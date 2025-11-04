<h2 align=center>Installation guide for Quok.it CLI on a GPU machine</h2>

Just enter your details and sign up here : https://quok.it/gensyn

![image](https://github.com/AgataGolik/images/blob/main/Zrzut%20ekranu%202025-11-04%20191829.jpg)
![image](https://github.com/AgataGolik/images/blob/main/Zrzut%20ekranu%202025-11-04%20182027.jpg)

Now check the email address you used. You should have a message from `support@quok.it` with that information:

![image](https://github.com/AgataGolik/images/blob/main/Projekt%20bez%20nazwy%20(29).png)

Now log in using the credentials you received here. https://app.quok.it/login 

Your API key will be needed in the next step.

Open a terminal on your GPU instance - for example, on Vast.ai.

If you’re currently inside a Gensyn screen session, you need to exit it by pressing `Ctrl + A, then D`. (You can return to it later by typing `screen -r gensyn`)

1) Add the Quok.it Repository:
```
sudo install -d -m 0755 /etc/apt/keyrings && curl -fsSL https://repo.quok.it/quok.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/quok.gpg >/dev/null && echo 'deb [signed-by=/etc/apt/keyrings/quok.gpg] https://repo.quok.it/ cross main' | sudo tee /etc/apt/sources.list.d/quok-stable.list >/dev/null && sudo chmod 0644 /etc/apt/keyrings/quok.gpg /etc/apt/sources.list.d/quok-stable.list && sudo apt-get update
```
2.) Install Quok.it CLI
```
sudo apt install quok
```
3.) Initialize and Authenticate
```
quok init
```

You’ll be prompted to enter your Quok API key. 
Paste it when asked – this links your CLI to your Quok.it account. Then `click ENTER`.

4.) Verify Installation
```
quok help
```
If you see a list of available commands (like audit, auditme, init), your setup is complete.

Now I’m opening a new screen session
```
screen -S quok
```
And there, I enter the following command

5. Run GPU Audit on This Machine
```
quok auditme
```
Enter provider (e.g., aws, akash, voltagepark, etc.): `vast` (for me it’s on Vast.ai — but you can use whatever platform you’re running on, like OctaSpace or any other)

And now go back to https://app.quok.it/ in the Dashboard section, you’ll find all the information you need about your GPU’s performance. :)




