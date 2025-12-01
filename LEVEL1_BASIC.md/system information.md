## Check CPU info
lscpu
cat /proc/cpuinfo

## Check RAM
free -h
cat /proc/meminfo

## Check Disks
df -h
lsblk

## Inspect Running Processes
top

## Install & Run htop
sudo apt install htop -y
htop

## List Processes
ps aux | grep service-name
