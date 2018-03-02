# SmartWires/Training/01-hello-git

Exercises:
1- Creating a Fork
A fork is a personal copy of a repository hosted by a provider such as GitHub. Create a fork and clone it.
Connecting to your GitHub profile with SSH
Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username or password at each visit. You can generate a new SSH key to use for authentication, then add it to the ssh-agent.

Generating a new SSH key
1-	Open Git Bash
2-	Paste the test Below, Substituting in your GitHub email address:
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

This creates a new ssh key, using the provided email as a label.
Generating public/private rsa key pair.

3-	When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]

4-	At the prompt, type a secure passphrase. Your passphrase is not visible in Git Bash window.
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]

Adding your SSH key to the ssh-agent

1-	Ensure the ssh-agent is running:
2-	# start the ssh-agent in the background
3-	$ eval $(ssh-agent -s)
4-	Agent pid 59566

5-	2- Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.

$ ssh-add ~/.ssh/id_rsa

Add the SSH key to your GitHub account.
To configure your GitHub account to use your new (or existing) SSH key, you'll also need to add it to your GitHub account.
1-	Copy the SSH key to your clipboard.
If your SSH key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.
$ clip < ~/.ssh/id_rsa.pub
# Copies the contents of the id_rsa.pub file to your clipboard

2-	In the upper-right corner of any page, click your profile photo, then click Settings.
3-	In the user settings sidebar, click SSH and GPG keys.
4-	Click New SSH key or Add SSH key.
5-	In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
6-	Paste your key into the "Key" field.
7-	Click Add SSH key.
8-	If prompted, confirm your GitHub password.

Now, you are ready to create a fork and clone it using git command. Get back to Git Bash and type the following newlines (replace username and FolderName in the command with your GitHub username and your desired name, respectively).
$ git clone git@github.com:username/FolderName.git
$ cd FolderName
$ ls
Now, you should have folder “foldername” in your local computer and GitHub profile.

2- Configure Git
Configure Git with your full name and email address:
$ git config --global user.name "FirstName LastName"
$ git config --global user.email "Email@smartwires.com"
$ git config user.name
FirsName LastName
$ git config user.email
Email@smartwires.com

This configures the default name and email address to use in commit messages. The --global flag causes the setting to apply to all repositories on your system, but per-repository configuration can override these. For more detail, see Customizing Git.

3- Making Changes
We're collecting pictures of the cutest animals on the web. Find a picture on a site with royalty free, public domain pictures, such as Pixabay.
Move the picture file to the folder “folderName” directory and then use the following command to add it to repository.
$ git add   … filedirectory…
For Example: $ git add C:/User/ Jonathan.Yu/ForderName/ wood-mouse-3077319_1920.jpg

If you want to see your changes, add --staged:
$ git diff –staged

We must now commit the changes to move them from the staging area to our local repository. Be sure to specify a descriptive message:
$ git commit --message="Adorable mouse"
[master e6833ec] Adorable mouse
 2 files changed, 2 insertions(+)
 create mode 100644 01 FolderName/wood-mouse-3077319_1920.jpg

4-Sharing Changes
The changes have been committed to your local repository, but they not be accessible by other team members. To make the changes visible, they need to be pushed to your fork:
$ git push
You should now be able to browse your changes in a browser by navigating to:  https://github.com/youraccount/training

5- Creating a Pull Request
The changes have been made in your local repository as well as your remote fork repository on GitHub. These changes need to be merged to our shared workspace by using a Pull Request. Follow GitHub's guide to create a pull request.
 
