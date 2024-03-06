# rawsecCTF2024

### Challenge: Resign Letter
### Category: Reverse Engineering
### Difficulty: Easy
### Points: 50  
### Description:

![RE with green](https://github.com/Cheese-Of-Truth/rawsecCTF2024/assets/145131434/0e43de75-419d-4f34-869a-a47b0c16242d)

### Walkthrough:

For this challenge, we got a Resign_letter_template.rar file. By extracting it, we got the Resign letter template.dotm file. Since it is a malware, so I didnt open it directly.
Instead, I used command "olevba <file> --decode " to analyse the file. From there, I observed that the dotm file will try to download "lenovo.exe" from a github repo when being executed.

![found lenovoexe](https://github.com/Cheese-Of-Truth/rawsecCTF2024/assets/145131434/83aa6143-671c-46dc-9f77-30a57ed6726f)

I copied the url to the browser and downloaded the exe file. By running strings <filename> and analysing the output, I found a suspicious long string.
Seem like the exe is trying to add an admin account into the victim's computer. Besides, there is a base64 encoded string inside which most likely will be the password.

![base64](https://github.com/Cheese-Of-Truth/rawsecCTF2024/assets/145131434/5712d365-f12a-44d2-a7fa-7905aafb9d28)

Copy the encoded string and decode it with cyberchef, we got the password which is p@ss123.

![cyberchef db64](https://github.com/Cheese-Of-Truth/rawsecCTF2024/assets/145131434/8f65d707-3b10-4cdb-9072-c682389c7ab6)


### Challenge: round and round
### Category: Cryptography
### Difficulty: Easy
### Points: 50
### Description:

For this challenge, a file named "cipher_2.txt" is provided. The cipher already have the flag format RWSC{}.

![ciphertxt](https://github.com/Cheese-Of-Truth/rawsecCTF2024/assets/145131434/94a16c48-b829-4901-aea2-6f8405265552)

I try to replace the numbers to alphabet by mapping 1=A, 2=B, 3=C ,...
After that, I guess they are using ROT so I calculate with my brain and it is!!
Hence, I guess out the cipher into alphabet form and put it into cyberchef. (29 is consider as "C" because after 26 it loops again)

![cryptoROT](https://github.com/Cheese-Of-Truth/rawsecCTF2024/assets/145131434/808de724-c51e-474f-8fc4-40da5897940b)

At first I thought the flag should be RWSC{PIZZA.. as the hint is pizza but i just couldnt make it. However, it is the correct flag. I guess there is something called pizzaini...
