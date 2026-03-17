# LabEx-Journey
This repo acts as documentation of subjects and activites I have engaged in through virtual guided labs offered by the site labex.io which I use to teach Cybersecurity concepts to me.

## Activities I've engaged in

- Using Hydra to Crack Passwords

Using a set up web browswer interface containing fields for entering a username and password, similar to that of login pages on many day-to-day websites. Utilizing a list of 500 worst passwords and usernames admin, user, and root, I passed them to a hydra command brute forcing the website and found 48 valid passwords, saving it to a file.
<img width="1428" height="397" alt="image" src="https://github.com/user-attachments/assets/eb2f7167-4ddd-42ff-8eaa-cc31f9908452" />

- Using Nmap on a network

I scanned my virtual machines network finding open ports hosting services such as ssh on port 22, ppp on port 3000, and nessus on port 3001. Passing some flags to it I can find the OS via `-O`, read targets from a file `-iL <file>`, do a SYN scan `-sS`, scan specific ports `-p`, save to a file `-oN <file>`or even use decoys by `-D <decoys>`. I can also scan a range of ips on a network like for example, `nmap 172.19.0.1-20` or scan an entire subnet `nmap 172.19.0.1/24`.
<img width="614" height="175" alt="image" src="https://github.com/user-attachments/assets/80d25be2-a4f5-4c75-b9d6-6bc05cc533ef" />

- Performing cryptographic operations like encrypting a message using Openssl

Using openssl, I created a file holding private information and via the commandline, passed flags specifying my encryption method, adding random data to prevent identical messages from looking the same when encrypted, and using password based key derivation function 2 to securely generate encryption keys from passwords.
<img width="791" height="400" alt="image" src="https://github.com/user-attachments/assets/5ddd746c-5ed5-4a5b-b07c-3b38af1636eb" />

- Setting up a port listener using netcat and connecting to it, using some of its functions
Using netcat, I had one terminal set up a listener on port 12345. Then opening another terminal, connected to port 12345 on localhost, allowing me to comunicate between the two terminals. I then set up the listener to output incoming data into a file, setting up netcat on the other terminal to send the file.

<img width="1054" height="231" alt="image" src="https://github.com/user-attachments/assets/3e5915f4-af18-4122-955a-b38a9860948a" />


