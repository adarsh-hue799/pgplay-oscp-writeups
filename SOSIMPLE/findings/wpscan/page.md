::: page
# wpscan {#wpscan .title}

\

We did wpscan for users and found this :

![](72-1.png)

We tried to bruteforce for **user max** and got the **password** :

![](72-2.png)

Lets see whats inside :

![](72-3.png)

We are **logged in**.

We tried to **upload a reverse shell** in many ways, by changing file
extension but that was all a **rabbithole**.

User max had **no permissions** and all that effort went to **vain**.

Lets analyse the **wpscan again** :

We found this which o**verlaps with the finding in the source** :

![](72-4.png)

![](72-5.png)

These both **overlap, lets research about them**.

Found this on **exploitDB** :

![](72-6.png)
:::
