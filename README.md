Create new services for content transformation
===


This project has 2 components. The first is creating a Mobi formatted ebook from Connexions content.  The second is creating an API that uses the SWORD API to accept payloads for editing.

Mobi
----
Mobi is the ebook format used by Kindle readers. Amazon has released an update to the mobi format. This project would take our existing mobi format code and update it to the new specs. It would also integrate the mobi code into the new Transformation Services

- Mobi format: www.amazon.com/kindleformat
- Current Mobi code: 
- Transformation Services Code: 
  - https://github.com/Connexions/rbit
  - https://github.com/Connexions/rbit-ext
 
Skills Needed
---

- HTML
- CSS
- Python


Sword API
===
Take the existing SWORD interface from Connexions and rewrite it for use with the new Transformation Services. SWORD accepts a zip file as a payload and returns an XML response.  The API would accept the payload, add a job to the work queue and return the proper XML.

- SWORD API Spec: http://swordapp.org/sword-v1/the-specification/
- Current SWORD API code: https://github.com/Rhaptos/rhaptos.swordservice.plone

Transformation Services Code: 

- https://github.com/Connexions/rbit
- https://github.com/Connexions/rbit-ext

Skills Needed

- XML
- Python


Enhance HTML5 Editor For Editing of OpenStax College Textbooks
===

Connexions is enhancing the Aloha editor to allow the semantic editing needed for textbooks.  The OpenStax College textbooks have special features that will require additional enhancements to Aloha.  The enhancements are

- Create an Aloha plugin for inserting XML Processing Instructions
- Enhance the Note plugin to allow additional class attributes to be added - See this mockup (http://mountainbunker.org/~maxwell/oerpub/editor-ideas/editor-38.html)  for ideas about how a class attribute change could be handled in a "Note to Reader". If you drag in a Note to Reader, click on the little label that says "Note" and you can switch it out. For attributes that will affect display, this same technique can be used. 
- Enhance Section headers so class attributes can be added

Relevant Links

- Demo of Editor: http://wysiwhat.github.com/Aloha-Editor/cnx/
- Editor Code: https://github.com/wysiwhat/Aloha-Editor
- Aloha Editor Home: http://aloha-editor.org/
- OpenStax College: http://openstaxcollege.org/

Skills Needed

- Strong Javascript skills
- HTML5
- CSS


Rich Content Query and Mining
===

Connexions has semantically rich content; why not let people run queries against it! Want to know how many exercises we have on Optics? Or which prerequisites could be read before reading a section of a book? We do too! In this project we wish to extend and integrate prototyped client-side visualization libraries with a live backend, to increase performance and enable “what if” realtime queries. New backend useful to drive alternative content viewing/using apps in the mobile space (see QuizCards)

Skills Needed

- Interest in data analytics
- Javascript (nodejs, jquery, requirejs)
- database and search interests (PostGreSQL, NOSQL, elasticsearch)

See https://github.com/philschatz/cnx.analytics and youtube: http://www.youtube.com/watch?v=LMiT5QlmhB0


Book Editing on Github
===

An EPUB3 Document is just a zip file of a bunch of HTML files and some spine files; why not enhance our Javascript Editor and edit books directly on Github (github even has a "Download as Zip" button)?

This would require adding features to our javascript editor and wire things up to github (loading images/CSS from private repositories for example).

Possible features:

- Support private repositories
- Support editing in MarkDown and autogenerating HTML files
- Handle Pull Requests
- Add tickets to content using GitHub's issue tracker

**Prototype:** https://github.com/philschatz/github-book and demo: http://philschatz.github.com/github-book/
**Tools:** CoffeeScript, requirejs, Backbone.js, Mustache/Handlebars, jQuery.Deferred

Relevant Links: 

- Javascript client to github's API: https://github.com/philschatz/github-js
- EPUB3 Spec: http://www.idpf.org/epub/30/spec


Emulating CSS for Paged Media
===

w3.org has some great specs for people that make textbooks but aren't supported by browsers. For example, dynamically calculating numbers to put into links (like "See Figure 4.13") and collating content at the end of a chapter/book (like solutions to exercises).

It would be great if we had an engine that "emulates" these rules (and maybe custom extensions) and "bakes" them into the resulting HTML file so they can be shown in a PDF or EPUB.

Some ideas of CSS features to implement:

- Looking up counters based on id (like "See Figure 4.13): Generated Content for Paged Media 
- Moving content to the end of a chapter/book (exercises): CSS3 Generated and Replaced Content
- Sorting a glossary (no spec in CSS yet)

**Prototype:** https://github.com/philschatz/oer.epubcss
**Tools:** LessCSS parser, node.js, PhantomJS


Integrate an annotation tool with the editor
===

Authors need ways to comment on revisions of their content and an annotation tool would be a useful feature to create comments. We could explore Annotator or Hypothes.is which is built on Annotator.  Connexions and OERPUB are enhancing the Aloha HTML5 editor to allow the semantic editing needed for textbooks. So the idea would be to create an Aloha annotation plugin..   

Relevant Links

- Demos of Editor: http://wysiwhat.github.com/Aloha-Editor/cnx/ , http://wysiwhat.github.com/Aloha-Editor/oerpub/
- Editor Code: https://github.com/wysiwhat/Aloha-Editor
- Aloha Editor Home: http://aloha-editor.org/
- Annotator project : http://okfnlabs.org/annotator/
- Hypothes.is project : http://hypothes.is/

Skills Needed

- Strong Javascript skills
- HTML5


Offline editing in the editor
===

Allow authors to edit textbooks in a browser the same way as online using the Aloha HTML5 Editor. This should work seamlessly. The experience of using the offline editor should be the same as using the online editor. The tricky part is to cache the offline data before synchronizing it again online. Synchronizing itself should be simple for the first version, because we do not want to handle merge conflicts at first. HTML5 offline web applications (limited to 5MB) works in all modern browsers but limits editing capabilities because it will not allow editing or caching of many or big images. Another approach which gives us a better offline experience is to support only the best browsers out there like Chrome (and Firefox hopefully) and build a Chrome (and Firefox) plugin which can store and host bigger offline content (similar to Google Docs offline caching/extension). The plugin will enable larger offline caching and hosting of the editor and its content.

Relevant Links

- Demos of Editor: http://wysiwhat.github.com/Aloha-Editor/cnx/ , http://wysiwhat.github.com/Aloha-Editor/oerpub/
- Editor Code: https://github.com/wysiwhat/Aloha-Editor
- Aloha Editor Home: http://aloha-editor.org/
- WHATWG & W3C Offline Web applications specification: http://www.whatwg.org/specs/web-apps/current-work/multipage/offline.html http://www.w3.org/TR/offline-webapps/
- Chrome extensions developer guide: https://developer.chrome.com/extensions/devguide.html

Skills Needed

- Strong Javascript skills
- HTML5
- Building Chrome extensions experience is a plus
