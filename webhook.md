# Generating SSH Key Pair and Linking it to GitHub

Execute the command `ssh-keygen -t rsa -b 4096 -C "youremail@.com" -f tech241-mushahid-jenkins` to create the SSH key pair.

## Steps to Link SSH Key to GitHub:

1. Sign in to your GitHub account.
2. Go to the "app" repository and proceed to settings by clicking on your profile picture.
3. Click on "Deploy keys" in the left sidebar.
4. Click on "New SSH key".
5. Assign a name to the key (for example, "Jenkins SSH key").
6. Copy and paste the public key file content into the "Key" field.
7. Click on "Add SSH key" to store it.



# Jenkins and Github Integration
## Jenkins Setup

*Step 1:* Copy the HTTPS URL from your Github repository and paste it into the project URL field.

*Step 2:* In the 'Source Code Management' section, choose 'GIT' and paste the SSH URL from your Github repository.


*Step 3:* Add credentials by copying the private key (the pair of the public key from the app repo with the same name and exact content).

*Step 4:* Change the branch name to main.

*Step 5:* In the 'Build Environment' section, select 'Provide Node & npm bin/folder to PATH' and choose 'SParta-Node-JS' for testing our app.



*Step 6:* In the 'Office 365 Connector', restrict the node agent's testing location to separate it from the Node master.

*Step 7:* Add your testing commands.



*Step 8:* Save the job. You are now ready for build and test.

# Creating a GitHub Webhook with Jenkins
## GitHub Configuration

*Step 1:* Navigate to your GitHub repository and select Settings.

*Step 2:* Click on 'Webhooks' and then on 'Add webhook'.

*Step 3:* Paste your Jenkins environment URL in the 'Payload URL' field. Add `/github-webhook/` at the end of this URL. Select 'application/json' in the 'Content type' and leave the 'Secret' field blank.



*Step 4:* In the 'Which events would you like to trigger this webhook?' section, select 'Let me select individual events'. Then, check 'Pull Requests' and 'Pushes'. Ensure the 'Active' option is checked and click on 'Add webhook'.

## Jenkins Configuration

*Step 5:* Click on 'New Item' in Jenkins to create a new project.

*Step 6:* Click on the 'Build Triggers' tab and then on the 'GitHub hook trigger for GITScm polling'. Alternatively, choose the trigger of your preference.



After completing these steps, Jenkins will execute the job every time changes are pushed or pulled from the app repository