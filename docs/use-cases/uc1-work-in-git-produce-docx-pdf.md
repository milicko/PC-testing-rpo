---
title: UC1 Collaborate in GIT and Deliver Professional DOCX & PDF
weight: 1
layout: docs
---

* Do you collaborate in Git?
* Do you like current DOCX editors?
* Do you need to deliver professional DOCX/PDF?

If answers are: __yes, no, yes__ respectively, you are at the right place.

In this section we will explain the workflow on how you can collaborate in Git and still produce and deliver high quality, professional DOCX and/or PDF using our solution (very convenient for DevOps and Agile teams). This concept is known as docs-as-code, or we like to call it docx-as-code.

High level steps are:

1. Import your docs (.md based) repo
2. Upload your corporate DOCX template (or use existing one)
3. Create a Table of Content structure out of .md files
4. Deliver your DOCX/PDF to the customer (shared link, email or similar)


A detailed workflow is outlined in the following UML diagram:

<!---
@startuml
skinparam sequence {
ArrowColor DodgerBlue
ActorBorderColor DodgerBlue
LifeLineBorderColor blue
LifeLineBackgroundColor DodgerBlue

ParticipantBorderColor DodgerBlue
ParticipantBackgroundColor DodgerBlue
ParticipantFontName Sans
ParticipantFontSize 17
ParticipantFontColor #A9DCDF

ActorBackgroundColor DodgerBlue
ActorFontColor DodgerBlue
ActorFontSize 17
ActorFontName Sans

}
title Collaborate in Git and Build Pro DOCX and PDF
autonumber
actor "Git User" as user
database "PuzzlesCloud" as saas
database "Git Project" as repo
group Git User workflow
   user -> saas : register
   user -> saas : import Git project (simple .md)
   saas -> repo : import Git project (simple .md)
   user -> saas : upload corporate DOCX template
   user -> saas : start a new document in our app
   user -> saas : create a Table of Content from Git .md docs
   user -> saas : save
   alt if pushing to repo
    user -> saas : push
    saas -> repo : push DOCX Template
    saas -> repo : push DOCX Table of Content
    saas -> repo : push updated DOCX and PDF
   else if downloading
    user -> saas : download DOCX or PDF
   else if sharing
    user -> saas : publish and share puzzlescloud link
   end
  alt if using git for updates
   alt if updating content
   user -> repo : commit new documentation version
   repo -> saas : your repo notifies us about the new version
   saas -> saas : generate updated DOCX and PDF
   alt if pushing to repo
     saas -> repo : push updated DOCX and PDF
   end
   else if changing DOCX template
   user -> repo : commit your new DOCX template
   repo -> saas : your repo notifies us about the new template
   saas -> saas : generate updated DOCX and PDF
   alt if pushing to repo
     saas -> repo : push updated DOCX and PDF
   end
   else if changing Table of Content (add/remove chapters, change order/heading level)
   user -> repo : commit your new Table of Content
   repo -> saas : your repo notifies us about the new ToC
   saas -> saas : generate updated DOCX and PDF
   alt if pushing to repo
     saas -> repo : push updated DOCX and PDF
   end
   end
  else if using PuzzlesCloud for updates
   alt if updating content
   user -> saas : update documents
   user -> saas : save and push
   alt if pushing to repo
     saas -> repo : push updated DOCX and PDF
   end
   else if changing DOCX template
   user -> saas : upload your new DOCX template
   user -> saas : save
   
   alt if pushing to repo
     saas -> repo : push DOCX Template
     saas -> repo : push updated DOCX and PDF
   end
   else if changing Table of Content (add/remove chapters, change order/heading level)
   user -> saas : Update Table of Content
   user -> saas : save
   alt if pushing to repo
     saas -> repo : push DOCX Table of Content
     saas -> repo : push updated DOCX and PDF
   end
   end
end
@enduml


preview: https://www.planttext.com/
-->

![Collaborate in GIT and deliver DOCX & PDF](/images/work-in-git-produce-docx-pdf.png "Collaborate in GIT and deliver DOCX or PDF")

1. Register (if not already done) and login to our application
2. Import a Git project where you have MarkDown based documentation.
3. Our application will connect to your repo and import it.
4. Upload your DOCX corporate template. For more details how to do it please check [Create docx Template](create-docx-template "Create docx Template").
5. Start a new doc in our application.
6. Create manually the structure (Table of Content) of the new document, based on MarkDown docs in your Git repo.
7. Save your new doc in our application 
8. **[If Pushing to Repo]** Push it to your Git repo.
9. Our App will push to your Git project uploaded DOCX template.
10. Our App will push to your Git project created DOCX structure (Table of Content).
11. Our App will push to your Git project new updated DOCX and PDF documents.
12. **[If Downloading]** Download DOCX or PDF to your local PC.
13. **[If Sharing]** Publish your version of the doc and share the link to your customer for download.
14. **[If Updating the Content]** You can update the content and commit the change to your repo.
15. Your repo through webhook service will notify our App about the change.
16. Our App will generate updated DOCX and PDF.
17. **[If Pushing to Repo]** Our App will push to your Git project new updated DOCX and PDF documents.
18. **[If Changing DOCX Template]** You can update the DOCX Template and commit the change to your repo.
19. Your repo through webhook service will notify our App about the new Template.
20. Our App will generate updated DOCX and PDF.
21. **[If Pushing to Repo]** Our App will push to your Git project new updated DOCX and PDF documents.
22. **[If Changing Table of Content]** You can update the Table of Content and commit the change to your repo. There are different possibilities: add/remove chapters/ .md docs, change order/heading level 
23. Your repo through webhook service will notify our App about the new Table of Content.
24. Our App will generate updated DOCX and PDF.
25. **[If Pushing to Repo]** Our App will push to your Git project new updated DOCX and PDF documents.

  **If using PuzzlesCloud for Updates**

This option is still in development, coming soon. 
