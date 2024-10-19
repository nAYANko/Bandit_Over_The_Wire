# Level 16>17
This level is solved using Nmap.
 
` nmap [host] -p<range> `
as
` Nmap localhost -p31000-32000 `

We get 5 open ports.

![bandit17](https://github.com/user-attachments/assets/67af163e-ed1b-4a7e-88d0-a11d2f95f073)

After connecting to the required port, we are provided with a private key for the next level, store it in a file and use it to log on to the next level.


****If the output shows unprotected private key use chmod 600 [file] to restrict access to the file.

![bandit17 1](https://github.com/user-attachments/assets/81bb584e-e2f5-459a-bf8a-67782618b38b)

# Level 17>18
` diff [file1] [file2] ` as ` diff passwords.old passwords.new `

Diff is used to compare files line by line.

![bandit18](https://github.com/user-attachments/assets/3d30e9b3-ec18-4eed-9aa3-62f50429e45f)

# Level 18>19
To use a command without maintaining connection with server,

` ssh bandit18@bandit.labs.overthewire.org -p 2220 “cat readme” `

![bandit19](https://github.com/user-attachments/assets/d28ed06b-872d-4482-a8fc-42882a0ee910)


# Level 19>20
Under the given file we have bandit20 level access so we can run cat command together with that to retrieve the password.

![bandit20](https://github.com/user-attachments/assets/c2d69a0e-204f-4d6b-82ca-5c5a83261473)

# Level 20>21
Here make connection to any port and give it the lvl20 pass, on the other tab the ./suconnect
will send the next level pass.

![bandit21](https://github.com/user-attachments/assets/702dca3c-04d4-45e8-b5bd-e21f6583d23b)

![bandit21 1](https://github.com/user-attachments/assets/6fefd483-1031-4214-8126-d3be85e71414)

**** Here -l is used to listen to incoming connections while -p is used to mention the port.












