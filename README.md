
# Verify Zero Knowledge Proofs with Succinct SP1
 

## Step 1: System Updates and Installation of Required Tools

### Update System Packages
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install cmake pkg-config libssl-dev build-essential -y
```

### Rust and Cargo Installation
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

source $HOME/.cargo/env
```

### Docker Installation
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update >/dev/null 2>&1
sudo apt-get install -y docker-ce docker-ce-cli containerd.io >/dev/null 2>&1
sudo docker run hello-world >/dev/null 2>&1
```
#### Check Docker version:
```bash
docker --version
```

## Step 2: Install SP1 Toolchain

### Download and Install SP1 
```bash
curl -L https://sp1.succinct.xyz | bash
source ~/.bashrc
sp1up
```

#### Check the version of the SP1 toolchain to make sure it is installed correctly:
```bash
cargo +succinct --version
```

## Step 3: Initialize and Configure SP1 Project

### Initialize New SP1 Project
```bash
cargo prove new fibonacci
cd fibonacci/script
```

### Run and Verify the Project (Note: This step may take a little longer.)
```bash
# First, execute the project without generating a proof to ensure that everything is set up correctly:
RUST_LOG=info cargo run --release -- --execute

# After confirming that the project runs successfully, generate and verify ZK proof:
RUST_LOG=info cargo run --release -- --prove
```

#### You can verify the successful installation of the SP1 CLI by checking the version of `cargo prove`:
```bash
cargo prove --version
```

**Join Chanel**

https://t.me/ZonaAirdr0p



