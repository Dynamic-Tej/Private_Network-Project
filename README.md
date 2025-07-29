# Private_Network-Project

A multi-VM private network application using Apache, PHP, and MySQL for secure data storage and file uploads. Built with VirtualBox and SSH-controlled infrastructure.

1.Virtual Machines Setup (in VirtualBox) Machines Created: WebServer1 – hosts the website (frontend + backend) DBServer – hosts MySQL database BackupServer – for future backup use (currently saved state) Configuration: OS: Red Hat (64-bit) Memory: ~2 GB per VM Networking: Adapter 1: NAT (Internet) Adapter 2: Bridged/Internal (for communication between VMs)
<img width="1920" height="1080" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/8775cb5a-528d-4deb-b38b-1134d3d56d16" />

2.Web Server Setup (WebServer1) Installed Software: Apache HTTP Server PHP Directory: /var/www/html/ Files: main.php – form to submit user data and file index.php – optional home or redirect page Uploads stored and user data inserted into DB
<img width="1920" height="1080" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/fb619f7f-2f90-4a9c-be0a-419596449102" />

3.SSH Communication (PuTTY) Used PuTTY to access both WebServer1 and DBServer using: IP: 192.168.0.210 (Private IP shown) Port: 22 User: nikhil, then root SSH commands confirm: Navigation to /var/www/html
File uploads and DB inserts tested
<img width="1920" height="1080" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/1cb3e96c-4557-4bc9-aad7-366483dbffa0" />

4.Database Server Setup (DBServer) Software Installed: MySQL Server 8.0+

DB Configuration: sql Copy Edit CREATE DATABASE udc; USE udc;

CREATE TABLE users ( id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255) NOT NULL, age INT NOT NULL, country VARCHAR(255), degree VARCHAR(100) ); Sample Query: sql Copy Edit SELECT * FROM users; Confirmed working as shown in screenshot.
<img width="1920" height="1080" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/495b464b-a774-49f6-be3c-fbcfc98d04b7" />

5.PHP File Upload and Data Insert (main.php) Form successfully: Captures user Name, Age, Country, Degree Uploads PDF Inserts values into users table Displays confirmation Uploaded file: RESUME_NIKHILDEEP YEMME 81262.pdf Success message: User data has been successfully stored in the database. File uploaded successfully.
<img width="1920" height="1080" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/968b9322-3ce6-4c79-a3be-9dcc5ce1b69c" />

6.Output Verification You verified: MySQL DB (udc) → Table (users) has entries PHP form inserted multiple records File upload works and is likely stored on server Apache + PHP running on WebServer1 MySQL accessible via root on DBServer
<img width="653" height="365" alt="68747470733a2f2f692e706f7374696d672e63632f514d7943424d34382f53637265656e73686f742d323032352d30372d32382d3133343130302e706e67" src="https://github.com/user-attachments/assets/a97b5e77-05e0-4390-a7a2-de05cc9dc17a" />
