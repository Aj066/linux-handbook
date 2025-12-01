# Apply coorect ownership
sudo chown -R devuser1:dev /var/www/app

# To change a file permissions
chmod 777 "filename"

# Use groups for collaboration
sudo chmod -R 770 /var/www/app

# Manage Directory ACLs (setfacl):
## grant group RWX
sudo setfacl -m g:dev:rwx /var/www/app

## Grant ops group read-only
sudo setfacl -m g:ops:rx /var/www/app

## Check ACL
getfacl /var/www/app

# Understanding umask:
## Temporary
umask 022

## Permanent(add to /etc/profile or ~/.bashrc):
umask 002
