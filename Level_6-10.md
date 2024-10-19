# Level 5>6
Use -size to specify size of the file followed by c for bytes.
` Find -size 1033c `

****To find a non-executable file, we use \! Before the -executable to denote not. Although this is not required here since only one file of given size exists. 

![bandit6](https://github.com/user-attachments/assets/126a7dc1-2056-4fe9-b435-64a4b44c5214)

# Level 6>7

Use the -user and -group tags along with -size with the find command to find the required file.


Lots of errors are shown and in-between them is the required file.


` find / -size 33c -user bandit7 -group bandit6 `

(forward slash is used to denote working directory, home in this case)

**** To get rid of all those “permission denied”, put 2>/dev/null at the end of the find command statement. 


Ref: https://exploreinformatica.com/how-to-exclude-all-permission-denied-messages-when-using-find-command/

![bandit7](https://github.com/user-attachments/assets/7bf25c65-4b88-476c-9436-5abcb65d5404)


# Level 7>8

Use grep piped with cat to search for required string.

` cat data.txt | grep “millionth” `

Ref: https://stackoverflow.com/questions/16961084/linux-shell-commands-cat-and-grep

![bandit8](https://github.com/user-attachments/assets/3e6651bb-1f89-48da-b79d-a7d3dd40a5aa)



# Level 8>9

Use the sort command to sort the repeating strings together, the uniq command is used to omit adjacent repeated lines. -c is used with uniq to count the repeating lines.

![bandit9](https://github.com/user-attachments/assets/3399e990-3de4-4b5f-9229-42c52944e9a4)

****To pull out the required string from this, we use the grep command, grep “1” ,
 Does nothing as its marks the 1’s in other strings, We use grep in reverse using -v tag

![bandit9 1](https://github.com/user-attachments/assets/bb2604d5-86e2-4800-93ee-9cd032cd755a)

# Level 9>10

Use the strings command piped with cat to get all the printable human readable strings.

![bandit10](https://github.com/user-attachments/assets/759b24c3-3cef-4a48-8a30-fcd83c6a5725)

For sorting out the “several =”  use grep “=” piped with the earlier syntax.

` cat data.txt | strings | grep “=” `

![bandit10 1](https://github.com/user-attachments/assets/83f1ad79-84cc-4619-8931-5bd96d6d87ea)

