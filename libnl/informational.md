found: 4 Mar 2017

```
Code: external/libnl/lib/attr.c (both android-7.1.1_r14 and master branch) 


int nla_memcpy(void *dest, struct nlattr *src, int count /* this is a design problem */) 
{ 
        int minlen; 

        if (!src) 
                return 0; 

        // minlen is an int, so this can potentially be a negative number. 
        minlen = min_t(int, count, nla_len(src)); 
        
        // minlen is cast to a size_t, and if it's a negative number it could possible be cast to a size exceeding the alloced size of "dest". Potential buffer or heap overflow. 
        memcpy(dest, nla_data(src), minlen); 

        return minlen; 
} 


// external/libnl/lib/attr.c 
int nla_len(const struct nlattr *nla) 
{ 
        // this doesn't validate nla_len which is __u16 
        return nla->nla_len - NLA_HDRLEN; 
} 
```

# patch suggestion
```
================= 
patch suggestion (external/libnl/lib/attr.c) 
================= 
// you can check minlen to ensure it's not negative, bigger issue is using integers to hold "count" 
size_t nla_memcpy(void *dest, struct nlattr *src, size_t count) 
{ 
        size_t minlen; 

        if (!src) 
                return 0; 

        // minlen is an int, so this can potentially be a negative number. 
        // min_t is still risky it will cast args to size_t. My nla_len patch prevents it from returning negative number. 
        minlen = min_t(size_t, count, nla_len(src)); 

        memcpy(dest, nla_data(src), minlen); 

        return minlen; 
} 


// alternatively this could return type __u16, and you could make sure return value isn't greater than nla->nla_len. 
size_t nla_len(const struct nlattr *nla) 
{ 
        // nla->nla_len is __u16 
        size_t result = nla->nla_len - NLA_HDRLEN; 

        if(result > UINT16_MAX) 
                BUG(); 

        return result; 
} 
```
