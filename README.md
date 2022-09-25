# To push new project to Git repository
echo "# Oauth" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/akanksha-93/Oauth.git
git push -u origin main

# To generate ssh key and add to account
akanksha@Akankshas-MacBook-Pro IdeaProjects % cd ~/.ssh
cd: no such file or directory: /Users/akanksha/.ssh
akanksha@Akankshas-MacBook-Pro IdeaProjects % ls -al ~/.ssh
ls: /Users/akanksha/.ssh: No such file or directory
akanksha@Akankshas-MacBook-Pro IdeaProjects % ssh-keygen -t ed25519 -C "akanksha.singla93@gmail.com"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/Users/akanksha/.ssh/id_ed25519):
Created directory '/Users/akanksha/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/akanksha/.ssh/id_ed25519
Your public key has been saved in /Users/akanksha/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:0MG7mC9KTQL3b4aQUeCODITcso3tXisjt/ZvsD2Htcs akanksha.singla93@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
|o.. .....        |
|oo o . ...       |
|. B + . ..       |
| = B + ..        |
|  + = ooS.       |
|   . Boo..       |
|  . o B.* .      |
| . B o.Boo       |
|  +.*ooooE.      |
+----[SHA256]-----+
Start ssh-agent to add above key to it :
akanksha@Akankshas-MacBook-Pro IdeaProjects % eval "$(ssh-agent -s)"
Agent pid 23692
akanksha@Akankshas-MacBook-Pro IdeaProjects % open ~/.ssh/config
The file /Users/akanksha/.ssh/config does not exist.
akanksha@Akankshas-MacBook-Pro IdeaProjects % touch ~/.ssh/config
akanksha@Akankshas-MacBook-Pro IdeaProjects % open ~/.ssh/config

Add below content
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519
  Hostname ssh.github.com
  Port 443

akanksha@Akankshas-MacBook-Pro IdeaProjects % ssh-add --apple-use-keychain ~/.ssh/id_ed25519
Identity added: /Users/akanksha/.ssh/id_ed25519 (akanksha.singla93@gmail.com)
akanksha@Akankshas-MacBook-Pro IdeaProjects % ls -al ~/.ssh
total 24
drwx------   5 akanksha  staff  160 25 Sep 21:37 .
drwxr-x---+ 25 akanksha  staff  800 25 Sep 21:34 ..
-rw-r--r--@  1 akanksha  staff   60 25 Sep 21:37 config
-rw-------   1 akanksha  staff  419 25 Sep 21:35 id_ed25519
-rw-r--r--   1 akanksha  staff  109 25 Sep 21:35 id_ed25519.pub
akanksha@Akankshas-MacBook-Pro IdeaProjects % cd ~/.ssh               
akanksha@Akankshas-MacBook-Pro .ssh % ls
akanksha@Akankshas-MacBook-Pro .ssh % cat id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIFAPdjxcbiSqQ9qH6KiEC0yAHEvNLDwXVm+5HTFI9YGs akanksha.singla93@gmail.com
Add above key to github a count profile in settings

# To set remote Git repository to ssh
git remote set-url origin git@github.com:akanksha-93/Oauth.git

