# findings
* TODO: the RCE one
* persistent XSS in [undisclosed] - need to wait until they patch it
* SQL injection in BSidesROC CTF scoring server [link](https://twitter.com/BSidesROC/status/320574435180552195) (6 Apr 2013) 
* XSS in hackertyper (26 April 2011)
```
pageTitle = </TITLE><SCRIPT> alert(2)</SCRIPT><!–
```


# 11 July 2017 - codewars
* XSS via linkedin profile URL (https://github.com/Codewars/codewars.com/issues/1032)
* XSS via stackoverflow profile URL (https://github.com/Codewars/codewars.com/issues/1033)
* twitter - they escape `"` and `<>`. Probably safe.
