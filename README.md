# LabEx-Journey
This repo acts as documentation of subjects and activites I have engaged in through virtual guided labs offered by the site labex.io which I use to teach Cybersecurity concepts to me.

## Activities I've engaged in correlating to the broader Cybersecurity

- Using Hydra to Crack Passwords

Using a set up web browswer interface containing fields for entering a username and password, similar to that of login pages on many day-to-day websites. Utilizing a list of 500 worst passwords and usernames admin, user, and root, I passed them to a hydra command brute forcing the website and found 48 valid passwords, saving it to a file.
<img width="1428" height="397" alt="image" src="https://github.com/user-attachments/assets/eb2f7167-4ddd-42ff-8eaa-cc31f9908452" />

- Using Nmap on a network

I scanned my virtual labs network finding open ports hosting services such as ssh on port 22, ppp on port 3000, and nessus on port 3001. Passing some flags to it I can find the OS via `-O`, read targets from a file `-iL <file>`, do a SYN scan `-sS`, scan specific ports `-p`, save to a file `-oN <file>`or even use decoys by `-D <decoys>`. I can also scan a range of ips on a network like for example, `nmap 172.19.0.1-20` or scan an entire subnet `nmap 172.19.0.1/24`.

<img width="614" height="175" alt="image" src="https://github.com/user-attachments/assets/80d25be2-a4f5-4c75-b9d6-6bc05cc533ef" />

- Performing cryptographic operations like encrypting a message using Openssl

Using openssl, I created a file holding private information and via the commandline, passed flags specifying my encryption method, adding random data to prevent identical messages from looking the same when encrypted, and using password based key derivation function 2 to securely generate encryption keys from passwords.
<img width="791" height="400" alt="image" src="https://github.com/user-attachments/assets/5ddd746c-5ed5-4a5b-b07c-3b38af1636eb" />

- Setting up a port listener using netcat and connecting to it, using some of its functions

Using netcat, I had one terminal set up a listener on port 12345. Then opening another terminal, connected to port 12345 on localhost, allowing me to comunicate between the two terminals. I then set up the listener to output incoming data into a file, setting up netcat on the other terminal to send the file.
<img width="1054" height="231" alt="image" src="https://github.com/user-attachments/assets/3e5915f4-af18-4122-955a-b38a9860948a" />

- Monitored a virtual labs network, capturing and analysing network traffic on a virtual lab using Wireshark

Setting up wireshark, I added my user to the wireshark group and configuring dumpcap to have elevated priveleges. I selected the interface I was using and began scanning the network. To test, I opened another terminal and curled http://example.com, then saved the packets and viewed them, explicitly searching for http and finding what I curled. Utilizing the filter, I specfied viewing of only `tcp && ip.addr == 104.18.26.120` which is the ip address of example.com. I also used the filter to view only the http get request and if the host contains example.com via `http.request.method == "GET" && http.host contains "example.com"`. Tested out saving filters and exported the http requests.
<img width="1885" height="981" alt="image" src="https://github.com/user-attachments/assets/3d1b02b8-f157-4f41-9a70-2d202d0a315a" />

- Brute forcing SSH with Hydra

Using a VM I installed the OpenSSH server package to turn my machine into an SSH server that can accept remote connections. I created a test user, set its password, configured SSH to allow password authentification, created a usernames and passwords file, as well as installing a tool named crunch to generate a more comprehensive password list specifying a minimum of 4 characters and a maximum of 6 with a allowed character set of 0-9. Though I dont use crunch in this since itd make the brute force much longer, a useful and interesting tool is noteworthy.

<img width="1427" height="457" alt="image" src="https://github.com/user-attachments/assets/1c61e5c9-733c-4613-b7bd-9119bc07c4d4" />

- Scanning a network for vulnerabilities and expanding use of Nmap
To start off, I do a regular scan of the network, finding basic information of the services hosted on the top 1000 ports and find a few. Digging deeper, I run a scan targetting specific ports I found in the original scan, and now checking the services version to see if I can spot vulnerabilities with outdated software. I find that the services are up to date so I instead run a scan with default scripts to gather more information, after running I find nothing much of use. I then decide to combine the service version with a vuln script to perform a broad vulnerability scan and save it to a file, once the scan is complete I see numerous vulnerabilities overall resulting in a vulnerable network.
<img width="1671" height="669" alt="image" src="https://github.com/user-attachments/assets/56b856d9-f7df-4bc2-a2dd-12bdfa8ced98" />
<img width="654" height="64" alt="image" src="https://github.com/user-attachments/assets/f499982d-04e6-4959-84e7-c087d7463c9a" />

- Creating a key and using it to encrypt a file with OpenSSL
I began by creating my file, storing the information I wanted encrypted and then saving it. Then using a tool offered by OpenSSL, I generated 32 bytes of random data and saved it in hexdecimal format to a file that Ill use as my key. Since the key can unlock my data, I made sure to change its permission to be only usable by the file owner. I then encrypted my file, using aes-256-cbc as my encryption cipher and using my created key file as the password.
<img width="784" height="420" alt="image" src="https://github.com/user-attachments/assets/a6db477e-8062-47d1-ac2b-a376eb218a7b" />

- Doing more filtering with Wireshark, using more of its tools and the command line version
Using an already made packet capture file, I view a detailed summary with capinfos targetting the file, showing off its file name encapsulation, number of packets, and much more. I then view the first 5 packets of the capture file, messing with filters offered by the flag `-Y`, and saving the filtered output to a file with `-w`. Finally, utilizing many flags offered by tshark, I create a packet capture file that is just as detailed as one in wireshark.
<img width="1474" height="261" alt="image" src="https://github.com/user-attachments/assets/b71133ae-e359-41d8-ae7a-0c82cf9f7e60" />

- Cracking ZIP passwords with John the Ripper
I start by cloning the git repository for john the ripper and specify the bleeding jumbo branch, as well as making the depth only one. I then cd into the directory and with the already installed tools, I make and clean. I then make some aliases so that I can use the commands anywhere. I test the aliases to check if they worked, then create a file needing to be encrypted and kept secret. Afterwards I use ZIP with its encryption feature putting a password onto my newly created zip file. Once thats done, I then use the zip2john tool where I input the zip file into, and it outputs details about the encrypted file including compression and encryption parameters. This information is vital to using John the Ripper so that it can crack the hash now having the hash and the encryption type. 
<img width="1312" height="566" alt="image" src="https://github.com/user-attachments/assets/f2513e26-a17b-4921-bed0-09ab3a292e79" />
