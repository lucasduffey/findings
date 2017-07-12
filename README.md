# android VULNS
* TODO: paste the notes on stuff they didn't care about
* TODO: add my patches here

# multiple XSS in codewars (11 July 2017)
* [UNFIXED] persistent XSS via clans name in codewars (https://github.com/Codewars/codewars.com/issues/1034)
  * found/reported much earlier (~3 June 2017), but they don't reply to any contact attempts
  * they partially patched on 12 July, but I can still exploit
  * NEW PoCS:
    * `"}; alert(/clan/);//`
    * `"; <script>alert(/clan/);</script>`
   * repro via
     * https://www.codewars.com/users/USER_YOU_ARE_FOLLOWING_BE_HERE/following
* persistent XSS via linkedin profile URL (https://github.com/Codewars/codewars.com/issues/1032)
* persistent XSS via stackoverflow profile URL (https://github.com/Codewars/codewars.com/issues/1033)
* [UNFIXED] persistent XSS in new kata via `description field` (https://github.com/Codewars/codewars.com/issues/1036)

# BSidesROC CTF scoring server (6 Apr 2013) 
* SQL injection in BSidesROC CTF scoring server [link](https://twitter.com/BSidesROC/status/320574435180552195) 

# XSS in hackertyper (26 April 2011)
```
pageTitle = </TITLE><SCRIPT> alert(2)</SCRIPT><!–
```

# android Metro PCS RCE (2012 or 2013)
* Metro PCS RCE: https://docs.google.com/presentation/d/18Fm2gWo36BrbH2rl0mFqB2bZ_s_sL7SV50c10lfBtSQ/edit?usp=sharing
