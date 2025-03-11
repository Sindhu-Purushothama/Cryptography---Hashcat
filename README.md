# Cryptography Project

## Objective
This project demonstrates various cryptographic techniques, including encryption, hashing, and digital signatures. The primary focus is on understanding and implementing secure data protection mechanisms.

### Skills Learned
- Symmetric and asymmetric encryption techniques
- Hashing for data integrity
- Digital signatures for authentication
- HMAC for message integrity verification
- Practical implementation of cryptography concepts

### Tools Used
- AES-256 for symmetric encryption
- RSA for asymmetric encryption and digital signatures
- SHA-256 for hashing
- HMAC for integrity verification

## Steps

1. Open your Ubuntu Linux VM: The below image shows the Ubuntu operating system designed for 64-bit ARM architecture.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/d6d4b868-2bfd-49d6-9b52-c934dc25aa6e/Untitled.png)

2. Open the CLI terminal: To open the terminal click on show application and click on terminal.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/aa00a7e1-5c1d-4694-843d-952dc71ddfac/Untitled.png)

This opens the new terminal.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/304a30e0-06fb-4a94-991f-03b6a5ae67cc/Untitled.png)

3. Update your package manager: **sudo apt update** 

Updating the package manager on Linux typically involves refreshing the package repository information and then upgrading installed packages to their latest versions.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/35bbb7f4-3571-43b3-b1c6-150def07e8ac/Untitled.png)

The **sudo apt update**  command updates the local database of available packages. It retrieves information on the latest versions of packages from the repositories configured on the system.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/27a7c219-b9d1-4b19-9e9a-1b346011d257/Untitled.png)

4. Download Hashcat: **sudo apt install hashcat**

Hashcat is an open-source (free) tool to crack passwords and hashes.Hashcat is available in the Ubuntu repository, so it can be  installed  using the `apt` package manager. This command will install Hashcat and all its dependencies.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/4c67a8e2-dabc-4145-b71d-9072e685eb58/Untitled.png)

I tried to install hascat, but got the below error. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/955a7fda-d782-4232-8a30-984efabc7d74/Untitled.png)

In order to fix the issue please refer the below link and follow the steps .

[hashcat : Depends: libminizip1t64 but it is not installable E: Unable to correct problems, you have held broken packages](https://stackoverflow.com/questions/78244374/hashcat-depends-libminizip1t64-but-it-is-not-installable-e-unable-to-correct)

After installation  of hascat use the below command to check the version.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/fc15fa99-fe3e-4222-b933-4a937174b80b/Untitled.png)

5. Learn more about Hashcat: hashcat  - -help ( no space between hypens )

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/196c8e05-1cef-4365-a612-dfd7289e95b8/Untitled.png)

6. Before using Hashcat, you need to download a wordlist.

a.Download the [rockyou.txt](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt&ved=2ahUKEwiCv6zp5reFAxXxT6QEHbFjD60QFnoECBQQAQ&usg=AOvVaw3snAERl1mU6Ccr4WFEazBd) wordlist on your Linux machine. ( If you’re using Kali Linux, you don’t need to download it. It will be in the /usr/share/wordlists directory. )

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/9e4e9ce3-0bac-408a-95a6-95cd1d7e269a/Untitled.png)

7. Now let’s crack some hashes.
    7a. Hash 1: fde24d80ac225175b4be937fdb1fab97

To figure out which type of hash it is.

use a website like [this one.](https://www.tunnelsup.com/hash-analyzer/)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/270c2bed-5524-43d6-b2a4-00261d1d7f52/Untitled.png)

7 b1. Now create a file to store the hash: touch filename

use the command touch to create the file.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/8e52e35d-1b49-4b1a-80e4-b3c2d6502dbc/Untitled.png)

7 b2. nano filename: This will open the file with a text editor.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/20ae2db6-d6af-4f04-9709-b6a125330be9/Untitled.png)

 This will open the file with a text editor.

7b3.  Copy the hash into the file.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/5374ca11-6678-4181-9e7f-013eeab2e6d2/Untitled.png)

7b4. Press CTRL + X to exit.

1. It will ask if you want to save. —> yes

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/bc17f37a-4c11-4561-b7db-c23505895277/Untitled.png)

1. Then it will ask if you want to change the name. Press enter to keep the same name.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/caf28887-154d-4f9c-b8ca-8267b5da4b99/Untitled.png)

7b5. You now have a file with the hash inside.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/5374ca11-6678-4181-9e7f-013eeab2e6d2/Untitled.png)

7c1. Now you can put in the command to start brute forcing the hash: hashcat -m 0 -a 0 sindhu.txt rockyou.txt

Make sure you are in the same directory as the rockyou.txt file.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/9e8b2d6f-99a6-4df0-9fa0-1638eb036336/Untitled.png)

The cracked password for the hash is shown below.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/9252c2d9-fd06-4016-97f2-7923cf7c1144/Untitled.png)

# Explanation of Flags and Hashcat.

- `m 0`: Specifies the hash type (0 is for MD5).
- `a 0`: Specifies the attack mode (0 is for a dictionary attack).
- `decrypt.txt`: The file containing the hash you want to crack.
- `rockyou.txt`: The wordlist file to use for the attack.

Hashcat will iterate through each line in `rockyou.txt`, attempting to find a matching plaintext password for each hashed password in decrypt.txt

***What is Hashcat?***Hashcat is a powerful and popular password cracking tool used primarily to recover lost or forgotten passwords through brute-force attacks, dictionary attacks, and hybrid attacks. It supports various hashing algorithms and can handle a wide range of hash types, including MD5, SHA-1, SHA-256, and many others commonly used in authentication and security protocols.Here are some key points about Hashcat:

1. **Password Cracking**: Hashcat is designed to crack hashed passwords. It takes hashed values as input and attempts to reverse them back into their original plaintext passwords by generating and testing potential password candidates.
2. **Hash Types**: It supports a wide variety of hash types and algorithms used for password hashing, including MD5, SHA-family (SHA-1, SHA-256, SHA-512), bcrypt, NTLM, and many others.
3. **Attack Modes**: Hashcat employs different attack modes:
- **Brute-force Attack**: Tries all possible character combinations.
- **Dictionary Attack**: Uses a predefined list of potential passwords.
- **Hybrid Attack**: Combines elements of both brute-force and dictionary attacks.
1. **Performance**: It is known for its speed and efficiency in cracking passwords, leveraging the parallel processing capabilities of modern GPUs (Graphics Processing Units) and CPUs (Central Processing Units).
2. **Usage**: Hashcat is commonly used by security professionals, penetration testers, and forensic experts to test the strength of passwords and to assess the security of systems by attempting to crack hashed passwords.
3. **Legal Use**: It's important to note that Hashcat, like other password cracking tools, should only be used in ethical and legal security testing scenarios with proper authorization.

7c2.Hash 2: 2d354a2fb4066717f86d5a5f633e14f8538018c3  

For the second hash, create a file called decrypt2.txt and copy the hash value as shown.

To figure out which type of hash it is.

use a website like [this one.](https://www.tunnelsup.com/hash-analyzer/)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/84e6269b-c4ac-43ab-b5d5-4a40e32118ad/Untitled.png)

Now you can put in the command to start brute forcing the hash: hashcat -m 100 -a 0 decrypt2.txt rockyou.txt

# Explanation of Flags and Hashcat.

- `m 100`: Specifies the hash type (100 is for SHA1).
- `a 0`: Specifies the attack mode (0 is for a dictionary attack).
- `decrypt2.txt`: The file containing the hash you want to crack.
- `rockyou.txt`: The wordlist file to use for the attack.

Make sure you are in the same directory as the rockyou.txt file.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/8e3270f4-33ae-49ea-9be2-18136ec4aa2f/Untitled.png)

The cracked password for the hash is shown below.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cbe69941-8337-427c-8610-3da01a118fd1/58b29fa7-bbe6-4993-ae73-2922fc37be29/Untitled.png)
---  
This project serves as a foundational exploration of cryptography techniques and their practical applications.

