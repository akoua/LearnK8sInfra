# cloud-provider-kind installation(MacOs) for loadbalancing
brew install cloud-provider-kind
sudo cp /opt/homebrew/Cellar/cloud-provider-kind/0.6.0/bin/cloud-provider-kind /usr/local/bin 
source $HOME/.zshrc
sudo cloud-provider-kind 

sudo cp /opt/homebrew/opt/docker-mac-net-connect/bin/docker-mac-net-connect /usr/local/bin
sudo brew services start chipmk/tap/docker-mac-net-connect

# Load a image on your kind cluster
kind load docker-image xxx/yyy:tagxx