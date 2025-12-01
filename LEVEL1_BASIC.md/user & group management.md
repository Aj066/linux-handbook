# To able to add user need to use the command of 
sudo adduser "username"

# To create groups
sudo groupadd "groupname"

# Add user in group 
sudo usermod -aG groupname "username"

# Configure Default Shells
sudo usermod --shell /bin/bash devuser1
