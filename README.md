These tutorial will guild you through setting up your git for project development

---

# SSH keys
To generate SSH keys on ubuntu

make sure that the email address same as one used to login to your github account

`
ssh-keygen -t rsa -C "example@example.com"
`
Press Enter

When promted to enter passphrase
 
Input a secure password
 
This provides an additional layer of security that require password incase your security bridge to your laptop or server

## Copy generated key 

`
cat /home/user/.ssh/id_rsa.pub
`

Copy

On Github 

`
 setting->SSH and GPG keys->New SSH key
`

Enter Title
Paste Key

# Create a new repository

Put your

- Repository name
- Description (optional)

Don't Initialize this repository with a README  for now as I will guild you to do that later on.

Select your prefered license 

Then Click Create repository
#Git
download git

`
sudo apt-get install git
`

make project directory

`
mkdir project
`

`
cd project
`

`
git init

`
# Create README.md

Using editor of your choice make `README.md`

# Connect to repository

`git remote add origin git@github.com:username/repository.git .`

`git fetch`

# Push to repository

`git add .`

`git commit -m 'initial commit'`

`git push -u origin master`

# Errors

incase of push error

`git pull --allow-unrelated-histories`




