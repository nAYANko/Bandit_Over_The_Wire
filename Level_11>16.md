# Level 10>11

We use basic base64 syntax with -d for decoding the encoded string.

` cat data.txt | base64 -d `

![bandit11](https://github.com/user-attachments/assets/89d5b332-2901-4cd1-b836-6a9cf7c22100)

# Level 11>12

To rotate the letters by 13 we can use the tr command piped with cat in the given format

` cat data.txt | tr ‘[a-z][A-Z]’ ‘[n-za-m][N-ZA-M]’ `

![bandit12](https://github.com/user-attachments/assets/7f2f7e84-db90-4209-a6c6-815b7d4685e8)

****You can also use rot13 command after installing the bsdgames package.

# Level 12>13

Create a temporary directory /tmp/boomboom

Copy data.txt to the directory

First use xxd with -r to reverse the hexdump

Store the output in a file

Use file command to check file type and run the corresponding unzip command

gzip is reversed by gunzip (while using gunzip make sure to change the file extension to .gz)

bzip2 is reversed by bunzip2 (the extension here should be .out but the computer adds it for you anyway

Extraction using tar is done using the format 

Tar –extract -f boom1

Here's the detailed implementation in screenshots:
![bandit13](https://github.com/user-attachments/assets/00497476-42b5-4a51-8cf4-db38889530be)

![bandit13 1](https://github.com/user-attachments/assets/adebdf63-3ab1-429d-844c-44e5c9822712)

![bandit13 2](https://github.com/user-attachments/assets/bf394c59-ff92-4d03-9114-b9086c4dac57)

# Level 13>14
We are provided with a private key called sshkey.private here to log on to the next level. Use -i with the ssh syntax as

` ssh -i [private key file] [user to be logged in to]@ [hostname] `

as

` ssh -i sshkey.priavte bandit14@localhost `

Usually this should give u access but in my case it kept connecting to the wrong port (port 22) for some reason so use -p to connect to the intended port.

![bandit14](https://github.com/user-attachments/assets/3aebc764-e778-4f27-b2d6-23fba88c230a)

# Level 14>15
Get the current level password by using cat on /etc/bandit_pass/bandit14, now run the nc command as
` nc [hostname] [port] `

as

` nc localhost 30000 `

Copy paste the lvl14 pass to get the next level pass or just pipe nc and cat together.

![bandit15](https://github.com/user-attachments/assets/69bcf31b-b779-4df6-b662-258ba41e9fd5)

# Level 15>16
Here we use openssl connection syntax

` openssl s_client -connect [host]:[port] `

as

` openssl s_client -connect localhost:30001 `

![bandit16](https://github.com/user-attachments/assets/1460cd91-9c8e-43b9-9aa7-dffd14fceb68)

****Here we use -ign_eof after the statement keeps the connection open read the response.















