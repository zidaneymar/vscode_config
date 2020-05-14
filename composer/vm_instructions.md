
# Create Ubuntu VM on Azure
remember to enable port 22 for ssh

# Set SSH config
```
ssh-add -k 'your key'
```

# Install NPM on Ubuntu
```
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```


## Make a directory for global installations:
```
mkdir ~/.npm-global
```

## Configure npm to use the new directory path:
```
npm config set prefix '~/.npm-global'
```

## Open or create a ~/.profile file and add this line:
```
export PATH=~/.npm-global/bin:$PATH
```

## Back on the command line, update your system variables:
```
source ~/.profile
```

# Optional: Config DNS For Your VM Composer Service
```
http://qika-composer.westus.cloudapp.azure.com:3000
```

# Config Inbound & Outbound Rule for VM:
> https://docs.microsoft.com/en-us/azure/virtual-machines/windows/nsg-quickstart-portal </br>

<p>Config Inbound Rule for port 3000 & 3979</p>
<p>Config Outbound Rule for port 3979</p>


# Install Dotnet
Please refer to this doc:
> https://docs.microsoft.com/en-us/dotnet/core/install/linux-package-manager-ubuntu-1804


# Try Composer
0. Build and Start Composer
    ```
    cd BotFramework-Compose\Composer
    yarn install && yarn build && yarn start
    ```

1. Create an Echo bot and Start
2. Open Emulator on your local desktop and config the endpoint like this: http:/your-vm-ip:3979/api/messages
3. Chat with the bot