# e-Dokyumento 
### Web-based Electronic Document Management System 
![ScreenShot](https://raw.githubusercontent.com/nelsonmaligro/e-Dokyumento/master/public/images/edokyu.png)

# Overview
e-Dokyumento is a web-based Document Management System that stores, organizes, indexes, routes, and tracks
electronic documents. It automates the basic office document workflow such as receiving, filing, routing, and approving
of hard-printed documents through capturing (scanning), digitizing (OCR Reading), storing, tagging, and electronically routing 
and approving (digital signature) of documents. 

# Features
### 1. Document routing and workflow 
   - users can freely select the department or branch to route the document.
### 2. Add file links to the document 
   - users can link or attach files to the main document. This is ideal for documents requiring attachments such as references and enclosures
### 3. Add notes or comments 
   - users can add notes or comments to the documents during routing. This is similar to manually attaching 'Post it'.
### 4. Annotations 
   - managers and bosses can draw and add text into the document when correcting. Upon saving of the annotated document, 
   he/she can return it to the originator.
### 5. PKI-based Digital Signature 
   - managers and bosses can electronically sign to approve the document. Every document signed has a corresponding control number 
   for tracking. 
   - Users can upload Digital Certificate (p12 format) to embed digital signature into the document. 
   (note: administrator must first upload the CA certificate in order to validate the user certificates)
### 6. Content Searching 
   - Files are scanned using Optical Character Recognition (OCR) and indexed to allow searching of files or documents through its content.
### 7. Store and index multiple file format 
   - Upload, store, and open documents with the following following format: pdf, docx, xlsx, pptx, txt, and odt.
### 8. Graphical monitoring of document routing 
   - routed documents are graphically mapped through line chart and pie chart. This allows effective monitoring of office communications.
### 9. Edit document through mapped drive 
   - document can be edited through mapped drive or SMB shared drive.
### 10. Send document to other users 
   - documents can be sent directly to users much like an email. This is ideal for documents to be internally communicated between the staff and manager within the department.
### 11. Intelligent Document classification using Machine Learning
### 12. Document Tracking using QR Code

#  New Features
### 13. File Explorer
    -  Browser-based file managing interface of the mapped drive 
### 14. Kanban Taskboard
    -  Monitors document routing using the Kanban Taskboard and allows basic functionality of a Kanban for workflow management.

# Installation 
### Method 1:  Using the ISO

     1. Download the ISO file from https://sourceforge.net/projects/e-dokyumento/files/e-DokyuV2.iso/download
     2. Burn ISO to CD or Boot on a VM and choose "Boot System Installer" 
     3. If asked to login, username: root and password: admin@123 
     4. During installation, delete any existing partition and create 2 partitions for SWAP and root (/) mount  
     5. Login and open the terminal. type "su" hit enter and type "admin@123" (or password entered during installation). 
     6. move drive folder from /opt/drive to root :  "mv /opt/drive /"
  
### Method 2:  Install on new Ubuntu Linux; download:

https://sourceforge.net/projects/e-dokyumento/files/Install%20e-Dokyumento%20on%20Ubuntu%20Linux.pdf/download

### Method 3:  Docker Container

     1. Clone https://github.com/nelsonmaligro/e-Dokyumento. 
     2. Edit the file "controllers/dbhandle.js" and change the mongodb connection from "mongodb://localhost/docMS" to "mongodb://mongo/docMS".
     3. Build the image - "docker-compose build".
     4. Run the image - "docker-compose up" 
        note: Dont forget to shutdown the container upon exit - "docker-compose down". This is to prevent error in mongoDB. 
 
# Demo: 
# https://e-dokyumento.herokuapp.com/
# https://edokyu.seillig.com/
  <pre><code>
  Default Accounts:
  Username                        Password            Privilege           Department/Branch
   1. staff-marketing             staff@123           STAFF               MARKETING
   2. manager-finance             manager@123         MANAGER             FINANCE
   3. staff-secretary             staff@123           SECRETARY           SECRETARY-RECEIVING
   4. boss                        boss@123            EXECUTIVE           GM
   5. boss.wannabe                boss@123            EXECUTIVE           EAGM
   6. administrator               admin@123           SysAdmin
</code></pre>
# Docker Hub:
### Pull e-Dokyumento from Docker hub : "docker pull nelsonmaligro/edokyumento"
### Run the image: docker run -p 443:443 -it nelsonmaligro/edokyumento

# Roadmap

  1. Android and IOS Versions
  2. Automate re-training of Machine Learning for improved document classification
  3. Online or web-based editing
  4. Integration with MS Active Directory for improved file server security
  5. Customizable Workflow
 

# Credit

1. node-pdfsign
2. @ninja-labs/verify-pdf
3. Tensor Flow and Keras for the Machine Learning
4. Hopding/pdf-lib
5. nisaacson/pdf-extract
6. nextapps-de/flexsearch
7. paulmillr/chokidar
8. schmich/instascan
9. riktar/jkanban
10. callmenick/Custom-Context-Menu


# License
GPL
