**7. C - Even more pointers, arrays and strings**


this headache


    101-crackme_password - a file that contains the password for the crackme2 executable.
        Steps to Get the Password
            a. Clone the file - crackme2
            b. Install openssl,
                Type the command: sudo apt install libssl-dev
            c. Edit the source list
                Type the command: sudo nano /etc/apt/sources.list
                Add this to the file: deb http://security.ubuntu.com/ubuntu xenial-security main
                Exit nano
                Type the command: sudo apt update
                Type the command: sudo apt install libssl1.0.0
            d. In the 0x06.c directory
                First run the file: $ ./crackme2
                Note the response
            e. Test the file type
                Do: $ file crackme2
                Note the response
            f. Do ltrace on your terminal
                Do: $ ltrace ./crackme2
                Note the last strings like this: strncmp("_=/usr/bin/ltrace", "jennieandjayloveasm=", 20) = -11
                Copy this string: jennieandjayloveasm
            g. Do this next on your terminal
                $ export jennieandjayloveasm=hey
                ltrace ./crackme2
                Note the response: strcmp("d8578edf8458ce06fbc5bb76a58c5ca4"…, "6057f13c496ecf7fd777ceb9e79ae285"…) = 46
                Copy the md5 hash: d8578edf8458ce06fbc5bb76a58c5ca4
            h. Go to this website to convert the md5 hash to string: md5 site
                the result is the abc123.
            i. Now enter the following command your terminal
                echo -n 'abc123' > 101-crackme_password
                chmod u+x 101-crackme_password
            j. Push to your github
