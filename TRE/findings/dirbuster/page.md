::: page
# dirbuster {#dirbuster .title}

\

Used dirbuster with a different type of wordlist
(**/usr/share/wordlists/dirb/big.txt**)

Got this :

![](87-1.png)

Checked **adminer.php** :

![](87-2.png)

Also checked **other directories** and found these :

![](87-3.png)

rest all directories were restricted and were not interesting

Found this one :

![](87-4.png)

Next we tried to **enumrate the mantis bug tracker using ffuf** and
found many **hidden directories**, but all those were just
**documentation**.

We found this interesting directory : **/config** :

![](87-5.png)

Enumerated **a.txt** and found **database credentials** :

![](87-6.png)

Lets use this **credentials**.

![](87-7.png)
:::
