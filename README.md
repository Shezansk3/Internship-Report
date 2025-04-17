
🕵️ Sniffing Attack using Wireshark
This project demonstrates how unencrypted login credentials can be captured over HTTP using Wireshark, a powerful network protocol analyzer. It is an educational demonstration intended only for ethical hacking and cybersecurity training purposes.

🎯 Objective
To capture and analyze login credentials (username and password) submitted via an HTTP form using Wireshark, highlighting the importance of using HTTPS for secure communication.

🧪 Tools Used

Tool	Purpose
Wireshark	Packet capture & protocol analysis
Web Browser	To simulate login interaction
OS	Windows
🌐 Target Website
URL: http://testphp.vulnweb.com

Login Page: /login.php

This site is intentionally vulnerable and publicly available for security testing and educational purposes.

📝 Procedure
Start Wireshark

Launch Wireshark and select your active network interface.

Begin packet capturing.

Apply HTTP Filter (Optional)

Filter by: http

For login packets: http.request.method == "POST"

Perform Login

Visit the target login page in your browser.

Use credentials:

Username: admin

Password: admin123

Stop Capture

Stop Wireshark to end packet capturing.

Locate HTTP POST Request

Find the POST request to /login.php.

Right-click → Follow → HTTP Stream

Analyze Data

You will see the raw data sent via POST, including the username and password in plain text.

📸 Captured Example

POST /login.php HTTP/1.1
Host: testphp.vulnweb.com
...
uname=admin&pass=admin123&login=login
