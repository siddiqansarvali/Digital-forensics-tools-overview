#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool


## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").


- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <br>
   <br>
  <p align="center">
    <img width="1920" height="1080" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/a058d105-5e7e-41a3-938c-3ca1253b175c" />

  </p>
  <br>
  <br>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
  <p align="center">
   <img width="1920" height="1080" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/504de240-cc91-44d7-9f3e-ad4d467176d0" />

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
<img width="1920" height="1080" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/0e7b822b-5841-4e70-b939-afe90fb4de9f" />

 </p>
  
  
### step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

 <br>
   <br>
  <p align="center">
<img width="1920" height="1080" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/b02c84e3-9121-422e-8a5a-c0b43517a100" />

 </p>
  <br>
  <br>
### step 4: If any Packets not found
- if any packets not found run the process again 
- and move to next step

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
