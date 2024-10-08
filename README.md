# Daisukes IPA Signer
IPA Signing API using zsign

# Setup
## Natively
1. Install [zsign](https://github.com/zhlynn/zsign.git)
```
sudo su -c "apt-get install git -y && git clone https://github.com/zhlynn/zsign.git && cd zsign && chmod +x INSTALL.sh && ./INSTALL.sh && cd build && cp zsign /usr/local/bin"
```

2. Install NodeJS and NPM
    ```console
    apt install nodejs -y
    apt install npm -y
    ```
3. Update NodeJS
    ```console
    npm install -g n
    n latest
    ```
    Reconnect to SSH
4. Install MongoDB
    ```console
    apt-get install gnupg curl
    curl -fsSL https://pgp.mongodb.com/server-7.0.asc | \gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \--dearmor
    echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
    apt-get update
    apt-get install -y mongodb-org

    Debian swap line 3 with
    echo "deb [ signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] http://repo.mongodb.org/apt/debian bullseye/mongodb-org/7.0 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
    ```
5. Install Modules
    ```console
    npm install
    ```
6. Modify .env

7. modify main.js and replace ```const domain = process.env.Domain || "https://replacewebsite.com";``` 

8. Run
    ```console
    node .
    ```
## Docker
1. clone repo
   ```console
   git clone --depth=1 https://github.com/daisuke1227/Daisukes-IPA-Signer.git
   ```
2. open up `docker-compose.yml` and change `DOMAIN` on line 9 (should be able to use `http://127.0.0.1:3000` if you're only hosting locally)
3. `docker compose up -d`
4. askuasign is now running locally on http://127.0.0.1:3000 !

I love you!
