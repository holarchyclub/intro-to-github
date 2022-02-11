# Creating and Managing Keys



### Creating a new key on your machine
Open your terminal, and type
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
This should return with:
```
Generating public/private algorithm key pair.
```
When prompted for a location, hit enter to use the default
```
Enter a file in which to save the key (/home/YOUR_USERNAME/.ssh/algorithm): [Press enter] 
```
Now choose a password
```
Enter passphrase (empty for no passphrase): [Type a passphrase]
```
Hit Enter
```
Enter same passphrase again: [Type passphrase again]
```
Note the folder it generated to, and change the permissions
```
chmod 400 ~/.ssh/id_rsa
```
Now start your ssh agent
```
eval "$(ssh-agent -s)"
```
Which should return
```
Agent pid #_A_NUMBER_
```
Add the new key to your ssh agent
```
ssh-add /home/YOUR_USERNAME/.ssh/id_rsa
```

### Adding the created key to your account
Display the contents of your public key
```
cat ~/.ssh/id_rsa.pub
```
Which should give you
```
_BIG DUMPED KEY CONTENTS_
```
Now select and copy the key contents, go to the top right of github, click your profile icon, navigate down to settings
In settings, navigate down the list to keys - > add new key
Paste the copied public key contents and hit save
