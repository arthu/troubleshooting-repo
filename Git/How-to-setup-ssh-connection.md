#How to setup SSH connection with Git
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

**Generate public/private key**
1. Open Git Bash.

2. Paste the text below, substituting in your GitHub email address.

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

keyfile will be saved in ~/.ssh/id_rsa


**Adding your SSH key to the ssh-agent**
Ensure the ssh-agent is running:
eval $(ssh-agent -s)

Add your SSH private key to the ssh-agent. 
ssh-add ~/.ssh/id_rsa

**Adding a new SSH key to your GitHub account**
clip < ~/.ssh/id_rsa.pub

git >> settting >> SSH and GPG Keys
Click New SSH key