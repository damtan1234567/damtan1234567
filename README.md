sudo su
apt update && apt install qemu-kvm -y
qemu-img create -f raw 2012r2.img 20G
wget -O- --no-check-certificate http://drive.muavps.net/windows/Windows2012r2.gz | gunzip | dd of=2012r2.img
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok -y
ngrok config add-authtoken 2QzuFHAmz3PnS9ViI9sqIhUeML3_4Uoxfnc2Bxvkc1tUCNQeb
ngrok tcp 3389
