COURSE PROJECT  
in the discipline "Fundamentals of microprogramming"  
ON THE TOPIC: "Implementation of a program for encrypting and decrypting data in Assembly language."   
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Annotation  
The purpose and objectives of the course work determined its structure. It consists of an introduction, two sections, a conclusion and a list of references.  
The first section examines the history of the emergence and development of encryption methods.  
The second section is devoted to the development of a software product, it describes the structure of the program and conducted testing of the program and analysis of the results obtained.  
The conclusion contains the results of the work done in the implementation of encryption methods.  
 The flowcharts describing the program structures and the code listing of the developed software product are presented.  
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------    
Content    
Introduction 4  
Theory 5  
1. Research and analysis of the subject area 5  
1.1 The history of the emergence and development of encryption methods 5  
1.2 Encryption methods 6  
Implementation of the program 10  
Block diagrams of the program 11  
Program code 13  
Screenshots of the program 20   
Conclusion 22  
References 23  
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Introduction  
Encryption is the transformation of information, making it unreadable to outsiders. At the same time, trusted persons can decrypt and read the original information.  
There are many ways to encrypt/ decrypt, but the secrecy of data is not based on a secret algorithm, but on the fact that the encryption key (password) is known only to trusted persons.  
Encryption appeared about four thousand years ago. The first known example of a cipher is considered to be an Egyptian text created around 1900 BC, in which characters that did not match  
them were used instead of the usual hieroglyphs for the Egyptians. Absolutely any object can be encrypted on a computer. Since the study of cryptography began in ancient times, the study   
of ciphers has already gone very far. But the problem is that as soon as the cipher is created, they very quickly find a way to decrypt it.  
The relevance of the course work - thanks to the course work, I have mastered new methods, functions and designs in Turbo Pascal, as well as expanded     

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
1. Research and analysis of the subject area  
1.1 The history of the emergence and development of encryption methods  
People have long used encryption as a way to protect information. The idea of hiding secret meanings and messages in text is almost as old as the art of writing itself.  
At the dawn of the Bronze Age, scribes in the Middle East were taught the art of deciphering confusing and encoded texts.   
Ancient scribes solved much more complex riddles. The most popular of these was the use of an acrostic, when a hidden message was read by putting together the first letters of each line of text.  
Over the centuries of its existence, mankind has come up with many ways to keep secrets.  
The degree of knowledge of encryption methods is quite high. Every year, many programs and literature dedicated to cryptographic systems are created. A cryptographic system is a family of cipher  
 transformations and a set of keys. There are Symmetric and Asymmetric cryptosystems.  
Symmetric cryptosystems (with a secret key systems) - these cryptosystems are built on the basis of keeping the encryption key secret. The encryption and decryption processes use the same key.  
The secrecy of the key is a postulate. Asymmetric cryptosystems (open encryption systems - public key systems) - the meaning of these cryptosystems is that different transformations are used
 for encryption and decryption. One of them, encryption, is absolutely open to everyone. The other, decryption, remains secret. At the moment, fairly stable systems are more often used,
systems with a fairly complex encryption algorithm. Due to the need for various objects to encrypt secret data and cryptographic systems do not stand still and are constantly being improved.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
1.2 Encryption methods  
The simplest cipher is A CIPHER WITH LETTERS REPLACED BY NUMBERS. Each letter corresponds to a number in alphabetical order. A-1, B-2, C-3, etc.  
Book Cipher  
In such a cipher, the key is a certain book, which is available to both the sender and the recipient. The cipher indicates the page of the book and the line, the first word of which is the solution.  
Decryption is not possible if the sender and the correspondent have books of different publication and release years. The books must be identical.  
A cipher with a code word  
Another easy way to both encrypt and decrypt. A code word is used (any word without repeating letters). This word is inserted in front of the alphabet and the remaining letters are added in order,  
excluding those that are already in the code word. Example: the code word is NOTEPAD.  
The original: A B C D E F G H I J K L M N O P Q R S T U V W X Y Z  
Replacement: N O T E P A D B C F G H I J K L M Q R S U V W X Y Z  
Digital tables  
Its parameters can be anything, the main thing is that the recipient and sender are aware. An example of a digital table.  
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Caesar's Cipher  
It is a historical example of a substitution cipher (1st century BC) described by the historian of Ancient Rome Suetonius. Gaius Julius Caesar used a cipher of his own invention in his correspondence.  
In relation to the modern Russian language, it consisted of the following. The alphabet was written out, then the same alphabet was written out under it, but with a cyclic shift of 3 letters to the left:  
ABVGDEEZHZIYKLMNOPRSTUFHTSCHSHYEYU  
WHEREVER YOU ARE, RSTUFHTS HSH SHYYY EYAABV  
Mathematical model  
If you match each character of the alphabet with its ordinal number (numbering from 0), then encryption and decryption can be expressed by formulas:  
where x is a plaintext character, is a ciphertext character, is the power of the alphabet (number of characters),- the key.  
A theoretical analysis of the literature allows us to identify a promising direction for the development of encryption methods. The paper proposes the creation of a program using three encryption methods:  
the Caesar cipher, the cipher with the substitution of letters with numbers and the Polybius cipher. All these ciphers are simple enough to understand and decrypt, but that's the goal - to create a custom  
program for children's development. The user will enter a word or sentence that he would like to encrypt. Then, using the encryption method, it will manually decrypt, and after it receives the result,  
it will check it using the program.  
The Polybius Cipher  
Caesar's system is not the oldest. Perhaps the most ancient of the known is the system of the Greek historian Polybius, who died 30 years before Caesar was born. Its essence is as follows: consider a rectangle,  
often called a Polybius board. Methods of opening single-alphabet systems Despite their simplicity in implementation, single-alphabet systems are easily vulnerable. Let's determine the number of different  
systems in an affine system. Each key is completely defined by a pair of integers a and b that define the ax+b mapping. For, a, there are j(n) possible values, where j(n) is an Euler function that returns  
the number of mutually prime numbers with n, and n values for b that can be used independently of a, except for the identical mapping (a=1 b=0), which we will not consider. Thus, we get j(n)*n-1 possible values,  
which is not so much: for n=33, there can be 20 values as a (1, 2, 4, 5, 7, 8, 10, 13, 14, 16, 17, 19, 20, 23, 25, 26, 28, 29, 31, 32), then the total number of keys is 20*33-1=659. Sorting through such a number  
of keys will not be difficult when using a computer. But there are methods that simplify this search and which can be used in the analysis of more complex ciphers.  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Multialphabetic systems  
Polyalphabetic substitution ciphers were invented by Lean Battista in 1568. The basic idea of multialphabetic systems is that throughout the text, the same letter can be encrypted in different ways. I.e.,  
replacements for the letter are selected from many alphabets depending on the position in the text. This is a good protection against simple frequency counting, since there is no single masking for each letter  
in the crypttext. These ciphers use multiple one-letter keys, each of which is used to encrypt a single character of plaintext. The first key encrypts the first character of the plaintext, the second - the second,   
etc. After using all the keys, they are repeated cyclically.
The Vernam cipher  
The Vernam cipher, or disposable notepad, was invented in 1917 by Major Joseph Mauborn and Gilbert Vernam of AT&T (American Telephone & Telegraph). In the classical sense, a disposable notepad is a large  
non-repeating sequence of key characters distributed randomly. It was originally a disposable tape for teletypes. The sender used each character of the key to encrypt only one character of the plaintext.  
Encryption is the addition modulo n (the power of the alphabet) of a plaintext character and a key character from a disposable notebook. Each character of the key is used only once and for a single message,  
otherwise, even if you use a notebook of several gigabytes in size, when the cryptanalyst receives several texts with overlapping keys, he will be able to restore the original text. It will shift each pair  
of ciphertexts relative to each other and count the number of matches in each position. if the ciphertexts are shifted correctly, the match ratio will increase dramatically. From this point of view, cryptanalysis  
will not be difficult. If the key is not repeated and is random, then the cryptanalyst, whether he intercepts texts or not, always has the same knowledge. A random key sequence combined with a non-random plaintext  
gives a completely random crypttext, and no amount of computing power will be able to change this.
In real systems, two identical tapes with random key digits are first prepared. One remains with the sender, and the other is transferred in an "unrecoverable" way, for example, by a courier with security,  
to the legitimate recipient. When the sender wants to transmit a message, he first converts it into binary form and places it in a device that adds two digits modulo to each digit of the message, read from   
the key tape. On the receiving side, the encoded message is recorded and passed through a machine similar to the device used for encryption, which adds (subtracts, since addition and subtraction modulo two are equivalent)  
modulo two digits read from the key tape to each binary digit of the message, thus obtaining the plaintext. At the same time, of course, the key tape must move absolutely synchronously with its duplicate used for encryption.  
The main disadvantage of this system is that for each bit of transmitted information, a bit of key information must be prepared in advance, and these bits must be random. When encrypting a large amount of data,     
this is a serious limitation. Therefore, this system is used only for transmitting messages of the highest secrecy. According to rumors, the "hotline" between the United States and the USSR was encrypted using  
a disposable notebook. Many of the messages of Soviet spies were encrypted using disposable notebooks. These messages are unsolved today, and will never be disclosed (unless there is a way to go back in time   
and get these notebooks    
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Overview of existing programs  
At the moment, programs for encrypting text have not yet been used for educational purposes, but there are many programs that encrypt information for the purpose of secrecy:Word is a free program for encrypting   
and decrypting texts. This reliable and easy-to-use application allows you to quickly encrypt and decrypt text using a password. - a file protection program. With this program, you can protect folders and files with  
the dual user identification function. - this is a free program that allows you to encrypt data on Windows Vista/XP/Seven, Mac OS X and Linux operating systems.Steganography is a program. which will help hide text or   
files inside images.
There are countless programs for encrypting files, most of them are simple and easy to use. Every user who is worried about the safety of their data needs to know about such programs and use them.  
Implementation of the program  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------    
Requirements for the software product  
When developing a software product, it was necessary to solve the following tasks:  
. Menu formation,  
. The formation of procedures that implement encryption methods  
. Displaying the result on the screen  
. Stop the program and exit.  
This program implements two encryption methods, so for ease of choosing a method, it was necessary to create a user-friendly interface.  
The program should have a simple control system. Therefore, the menu uses the most concise commands and answers to them. This greatly facilitates the user's work.  
The essence of the subroutine is that the commands are displayed sequentially on the screen:  
First, the user must select the method by which he wants to encrypt the text. The screen displays - "Choose the encryption method 1-Caesar cipher, 2-cipher with letters replaced by numbers"  
The user selects by pressing the number of the cipher he needs.  
If he does not want to encrypt or has already finished the lesson, then he should press 0 to exit the cycle. A message with this information is displayed on the screen along with all the previous "To exit, press 0".  
The menu is controlled by the keyboard: to select, press the desired number and ENTER.  
After launching the software product, a menu appears on the screen, consisting of a suggestion to select a cipher and exit the program.  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------    
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/0599904f-6251-4c63-8e3f-862a8d682685)    
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/174dd3bf-6d03-4a78-b60c-1b1f4aa0d195)    
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/b2210116-12c1-426d-b8ef-6148011c395b)    
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/22e759d2-77bd-4326-a643-6b9890d7dcd7)        
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/19bb4eef-0bf7-48ee-94a5-c5442ac36b20)      
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/ff6043ad-70ac-4d9f-a60e-edfa0bd9bdd4)      
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/441300b6-bc99-4908-9495-0e4325ac2ddb)  
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/22ca7966-f336-4988-88c9-139042ed092b)  
![image](https://github.com/Semenovla/Course-project_OMP_Semenov_L_A_Second_cours/assets/106269089/b2b19a8f-0594-488c-9659-340b64b23adc)  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Analysis of the results obtained:  
During the testing of the software product, it was revealed that the goal was to create a software product that implements two encryption methods - and all the tasks of the course work were completed.  
As a result of testing, some inaccuracies in the decoding of the text were revealed, which need to be improved. But in general, the program works with generally accepted standards about text encryption.  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------  
Conclusion  
In the process of writing a term paper on the topic "creating a software product that implements various methods of text encryption", the goal was achieved.  
In order to achieve this goal, the following tasks were solved:  
. Similar software products have been studied,  
.	The theoretical information required to solve the task has been studied,  
.	The acquired knowledge is systematized and generalized  
.	A software product has been created that implements three encryption methods.  
During the development of the software product, functions were learned that convert information from a numeric type to a string type and vice versa, conditional if...then operators were also learned..else and for. … to…do.  
During the testing of the software product, the following shortcomings were identified:  
.	Errors are detected during the operation of the program.  
.	The menu in the program is not very user-friendly.  
Summing up, we can say that with the help of this software product, anyone, at any age, can encrypt and decrypt information.  
  



