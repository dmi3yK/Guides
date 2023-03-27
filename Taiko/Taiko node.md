## Taiko node

|System Requirements| |
|----|----------------|
|CPU|	8 cores         |
|RAM| 32 GB           |
|SSD| 50 GB           |
|OS | Ubuntu 20.04    |

#### Docker install

```bash
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg > /dev/null

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

# Check  installation is successful
sudo docker run hello-world

# Example output
# Hello from Docker!This message shows that your installation appears to be working correctly.
```

### Install Taiko
[Alchemy](https://www.alchemy.com/)

[Sepolia faucet](https://sepoliafaucet.com/)

```bash
git clone https://github.com/taikoxyz/simple-taiko-node.git

cd simple-taiko-node

cp .env.sample .env

nano .env

# Edit by
L1_ENDPOINT_HTTP=https://Alchemy
L1_ENDPOINT_WS=wss://Alchemy
ENABLE_PROVER=true or false
L1_PROVER_PRIVATE_KEY=YOUR_PRIVATE_KEY_MM
```
### Run node in background
```bash
docker compose up -d

# check logs
docker compose logs -f

# stop node
docker compose down
```
