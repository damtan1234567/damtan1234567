sudo su
apt update && apt install qemu-kvm -y
qemu-img create -f raw 2012r2.img 20G
wget -O- --no-check-certificate http://drive.muavps.net/windows/Windows2012r2.gz | gunzip | dd of=2012r2.img
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok -y
ngrok config add-authtoken 2L1xcRxX6HCIbHEYSsevbTb84tW_Y47qA74aRJVuB1x8EEuv
ngrok tcp 3389
