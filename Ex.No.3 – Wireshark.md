#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool


## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").


- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <br>
   <br>
  <p align="center">
  <img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/7b4199c8-c62c-4122-8a86-9fee5c4cd052" />
  </p>
  <br>
  <br>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
  <p align="center">
  <img width="1915" height="1199" alt="image" src="https://github.com/user-attachments/assets/657a7947-c9f8-4f01-88c0-5ddab2b85fb7" />
 </p>
  <br>
  <br>

  ### Step 2: Generate Login Traffic
  - Open a web browser and navigate to http://testphp.vulnweb.com/login.php.

- Enter any dummy credentials. For this example, we'll use:

   Username: testuser

   Password: password123

- Click the login button. The login will fail, but the data has already been sent across the network.

 <br>
   <br>
  <p align="center">
<img width="1916" height="1149" alt="image" src="https://github.com/user-attachments/assets/7d2d782c-2c77-4dfa-bfe5-3760489949bb" />
 </p>
  
  
### step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

 <br>
   <br>
  <p align="center">
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/8557c1c5-a6ae-4426-b9de-93ecf0997a59" />
 </p>
  <br>
  <br>

### step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

Hypertext Transfer Protocol

HTML Form URL Encoded

- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

 <br>
   <br>
  <p align="center">
  <img width="1919" height="1195" alt="image" src="https://github.com/user-attachments/assets/3b2833a8-7008-4bb7-8f67-c295049e9364" />
 </p>
  <br>
  <br>

---

## Result
The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network:

This result confirms the inherent security flaw of the HTTP protocol. Any sensitive data sent over HTTP is transmitted openly, making it trivial to intercept.
