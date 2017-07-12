# misc findings
* TODO: the android RCE one

# XSS in hackertyper (26 April 2011)
```
pageTitle = </TITLE><SCRIPT> alert(2)</SCRIPT><!–
```

# BSidesROC CTF scoring server (6 Apr 2013) 
* SQL injection in BSidesROC CTF scoring server [link](https://twitter.com/BSidesROC/status/320574435180552195) 

# codewars vulns (11 July 2017)
* persistent XSS via clans name in codewars (https://github.com/Codewars/codewars.com/issues/1034)
  * found/reported much earlier (~3 June 2017), but they don't reply to any contact attempts
  * pretty sure it's still vulnerable after "patch". Zero recognition, so I'm not going to bother looking.
* persistent XSS via linkedin profile URL (https://github.com/Codewars/codewars.com/issues/1032)
* persistent XSS via stackoverflow profile URL (https://github.com/Codewars/codewars.com/issues/1033)
