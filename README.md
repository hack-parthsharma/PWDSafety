<p align="center">
  <b>Command line tool that checks how much a password is safe</b><br>
  <sub>
    Coded with 💙 by Sharma Parth
    
**This tool doesn't store any information!!**  
**Remember, never use personal information in your password!**  
 - Use a password manager (I recommend [BitWarden](https://bitwarden.com/))  
 - Don't use the same password for different services  
 - Enable 2FA when possible  

Example :bar_chart:
----------

[![asciicast](https://asciinema.org/a/406710.svg)](https://asciinema.org/a/406710)

Get Started 🎉
----------


### From source

- First of all, clone the repo locally

  - `git clone https://github.com/hack-parthsharma/PWDSafety.git`

- pwdsafety has external dependencies, so they need to be pulled in:

  - `cd pwdsafety/cmd && go get && cd ..`

- Linux (Requires high perms, run with sudo)

  - `make linux` (to install)

  - `make unlinux` (to uninstall)

- Windows (executable works only in pwdsafety folder. Alias?)

  - `make windows` (to install)

  - `make unwindows` (to uninstall)

Description 🔦 
----------

It reads from standard input the entered password.  
First, it searches if the password or the password reversed is a well known pwd.  
Then, just do little calculations, checking if the basic rules are respected, like if there are UPPERCASE CHARS, lowercase chars, numb3rs and symbols.  
It stores the length of the password and the ratio [ unique different chars / total chars].  
It calculates then the entropy of a password.  
Password entropy is a measurement of how unpredictable a password is.  
The formula for entropy is:  
              ![formula](https://github.com/hack-parthsharma/images/pwdsafety/formula.png)  
              
Where:
- E = password entropy  
- R = pool of unique characters  
- L = number of characters in your password  
- Then R^L = the number of possible passwords  

When the score <= 68(reasonable) it generates a random password.  

Scoring 💯
----------

**Max score: 100**

**Scores:**
  - Very weak: 0 - 35
  - Weak: 36 - 59
  - Reasonable: 60 - 68
  - Strong: 69 - 80
  - Very strong: 81 -100
  
**Scoring parameters:**
  - Found in known password
  - Found in known password reversed
  - Password composition:
      - numbers
      - symbols
      - uppercase
      - lowercase
  - Unique different characters
  - Length
  - Entropy

