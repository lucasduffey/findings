# findings
* TODO: the RCE one
* SQL injection in BSidesROC CTF scoring server [link](https://twitter.com/BSidesROC/status/320574435180552195) (6 Apr 2013) 
* XSS in hackertyper (26 April 2011)
```
pageTitle = </TITLE><SCRIPT> alert(2)</SCRIPT><!–
```


# 11 July 2017 - codewars
* persistent XSS via clans name in codewars (https://github.com/Codewars/codewars.com/issues/1034)
  * found a lot earlier (~3 June 2017), but they didn't reply to emails
* persistent XSS via linkedin profile URL (https://github.com/Codewars/codewars.com/issues/1032)
* persistent XSS via stackoverflow profile URL (https://github.com/Codewars/codewars.com/issues/1033)
* twitter - they escape `"` and `<>`. Probably safe.
