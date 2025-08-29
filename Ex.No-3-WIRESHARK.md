#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool


## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").


- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <br>
   <br>
  <p align="center">
  <img width="1155" height="688" alt="image" src="https://github.com/user-attachments/assets/28b8635a-a3d2-4efc-9ed4-ab4b39f96ce5" />

  </p>
  <br>
  <br>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
  <p align="center">
  <img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/fe34867f-be37-49ee-b73d-c87bc3f51c76" />
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
<img width="1559" height="963" alt="image" src="https://github.com/user-attachments/assets/1a5dd68e-d041-414c-86ec-eef4794d0e46" />
 </p>
  
  
### step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

 <br>
   <br>
  <p align="center">
<img width="1919" height="517" alt="image" src="https://github.com/user-attachments/assets/24898bfb-4f11-4c3c-83aa-ac994cb3fdde" />

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
  <img width="921" height="561" alt="image" src="https://github.com/user-attachments/assets/b4403935-01b3-4678-81c9-bd1ad67c05bf" />
 </p>
  <br>
  <br>

---

## Result
The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network:

This result confirms the inherent security flaw of the HTTP protocol. Any sensitive data sent over HTTP is transmitted openly, making it trivial to intercept.
