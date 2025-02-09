## 4. Web Deployment & Cloud Setup

### How to Set Up a Web Server with Rust and Actix

#### Install Rust on DigitalOcean Droplet
```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

#### Initiate a New Project
```sh
cargo new actix-web-server && cd actix-web-server
```

#### Add Dependencies in Cargo.toml
```toml
[dependencies]
actix-web = "4"
```

#### Write a `main.rs` Server File and Run
```sh
cargo run
```

---

### How to Deploy Ruby on Rails on DigitalOcean

#### Create a DigitalOcean Droplet and SSH into the Server
```sh
ssh username@your_server_ip
```

#### Update the Server
```sh
sudo apt update && sudo apt upgrade -y
```

#### Install RVM and Ruby
```sh
sudo apt install curl gpg
\curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 3.2.2 
rvm use 3.2.2 --default
```

#### Install Node.js & Yarn
```sh
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
sudo npm install -g yarn
```

#### Install PostgreSQL
```sh
sudo apt install postgresql postgresql-contrib libpq-dev
```

#### Setup PostgreSQL
```sh
sudo -i -u postgres 
createuser -P myappuser  
createdb -O myappuser myappdb 
exit
```

#### Clone and Deploy Rails App
```sh
git clone https://github.com/my-repo/my-app.git myapp 
cd myapp 
bundle install 
rails db:migrate
```

#### Run Server
```sh
rails server -b 0.0.0.0 -p 3000
```

---

### How to Deploy Multiple MERN Apps to DigitalOcean

#### Clone Two Applications from GitHub
```sh
git clone https://github.com/my-repo1.git app1 
git clone https://github.com/my-repo2.git app2
```

#### Install Dependencies
```sh
cd app1 && npm install && cd .. 
cd app2 && npm install && cd ..
```

#### Edit `package.json` for Each App and Allocate Different Ports
```json
"scripts": { 
     "start": "PORT=4000 node server.js" 
}
```

#### Run Applications
```sh
npm start
```

#### Install and Set Up Nginx as Reverse Proxy
```nginx
server { 
      listen 80; 
      location /app1 { 
          proxy_pass http://localhost:4000; 
      } 
      location /app2 { 
          proxy_pass http://localhost:5000; 
      } 
}
```

---

### How to Set Up Maven in a DigitalOcean Droplet

#### Install and Check Maven
```sh
sudo apt install maven
mvn -version
```

#### Create a Maven Project
```sh
mvn archetype:generate -DgroupId=com.example -DartifactId=myapp -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
cd myapp
```

#### Build Project
```sh
mvn package
```

---

### How to Set Up a WordPress Droplet in DigitalOcean

#### Create a New Droplet
- Select the **WordPress 1-Click App** from the Marketplace.

#### Connect via SSH
```sh
ssh root@your_server_ip
```

#### Configure WordPress
- Open a browser and navigate to:
  ```
  http://your_server_ip
  ```
- Follow the setup wizard:
  - Select Language
  - Enter Database details
  - Set Admin credentials
  - Click **Install**
