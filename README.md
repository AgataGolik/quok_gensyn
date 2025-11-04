<h2 align="center">🚀 Installation Guide for Quok.it CLI on a GPU Machine</h2>

### 1. Sign up for Quok.it
Go to [https://quok.it/gensyn](https://quok.it/gensyn) and enter your details to create an account.

![signup](https://github.com/AgataGolik/images/blob/main/Zrzut%20ekranu%202025-11-04%20191829.jpg)
![signup2](https://github.com/AgataGolik/images/blob/main/Zrzut%20ekranu%202025-11-04%20182027.jpg)

---

### 2. Check your email
You’ll receive a message from `support@quok.it` containing your login credentials and API key.

![email](https://github.com/AgataGolik/images/blob/main/Projekt%20bez%20nazwy%20(29).png)

---

### 3. Log in
Use the credentials from your email to log in at [https://app.quok.it/login](https://app.quok.it/login).  
Your **API key** will be required later, so keep it handy.

---

### 4. Open your GPU terminal
Open a terminal on your GPU instance – for example, on **Vast.ai**.  
(You can also use **OctaSpace**, **Akash**, or any other GPU provider.)

If you’re currently inside a *Gensyn* screen session, exit it with:

`Ctrl + A, then D`

You can return to it anytime with:

```
screen -r gensyn
```


---

### 5. Add the Quok.it Repository
```bash
sudo install -d -m 0755 /etc/apt/keyrings && \
curl -fsSL https://repo.quok.it/quok.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/quok.gpg >/dev/null && \
echo 'deb [signed-by=/etc/apt/keyrings/quok.gpg] https://repo.quok.it/ cross main' | sudo tee /etc/apt/sources.list.d/quok-stable.list >/dev/null && \
sudo chmod 0644 /etc/apt/keyrings/quok.gpg /etc/apt/sources.list.d/quok-stable.list && \
sudo apt-get update
```

### 6. Install the Quok.it CLI
```
sudo apt install quok
```

### 8. Initialize and Authenticate
```
quok init
```


When prompted, paste your Quok API key and press `ENTER`
This links your CLI to your Quok.it account.

8. Verify the Installation
```
quok help
```

If you see a list of available commands (like audit, auditme, init), your setup is complete ✅

### 9. Start a new screen session
```
screen -S quok
```

### 10. Run GPU Audit on This Machine
```
quok auditme
```

When asked for the provider (e.g. aws, akash, voltagepark, etc.), enter:

`vast`


(For me it’s on Vast.ai — but you can use whatever GPU platform you’re running on, like OctaSpace or any other.)

If you want exit: `Ctrl + A, then D`
======================================================================================================
Check Your Dashboard

Go back to https://app.quok.it/

In the Dashboard section, you’ll find all the details about your GPU’s performance and usage stats. 🎯

Done! You’ve successfully installed and linked Quok.it CLI on your GPU machine.
=======================================================================================================

If you need support, go to the discord and #🐻︱quok·it-support channel. https://discord.com/channels/852932483691577395/1418607446871506974 

You can ask for help there chochotrain229 is part of the Quok support team.
