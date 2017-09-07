# Prep Work

{% hint style='danger' %}

If this is your first time joining us for Coding & Cocktails, you'll want to [install our tools](http://bit.ly/CnCTools) before you go any further.

{% endhint %}

### 1. <a href="slack://channel?team=T06BZHS4U&id=C0BGBKGG6">Click Here to Open Slack</a>

If you have a tip that helped you with a step on the worksheet, you can easily share it with the group in Slack. Or if there are any issues with the worksheet [we make typos or there's an update to a tool that we didn't catch before the session], we may post updates in Slack. Plus, after class is over, Slack becomes a tool for you to gain access to mentors as you go through the homework, or any other questions that arise.

{% hint style='danger' %}

If you're using a Chromebook, skip down to the Cloud9 instructions at the bottom.

{% endhint %}


### 2. Install/Update Node.js & npm {#install-nodejs}

{% hint style='danger' %}

If you joined us in May or August, you might have installed Node.js & **npm**, but you'll still want to update to the latest version of Node.js & **npm**.

{% endhint %}

1.  Open Git Bash or iTerm2

  {% hint style='info' %}

  The "terminal" and "command line" (aka CLI, command line interface) are the same thing.
  - On Windows, we use **Git Bash**
  - On Mac, we use **iTerm2**

  {% endhint %}

2.  In your CLI, type: `node --version`

    Do you get a version number [_Version **8 or greater** required._]?

    1. No version number [something like `node: command not found`]. You need to install Node.

      <!--sec data-title="Mac - Install Node" data-id="sectionInstallMac" data-show=true data-collapse=true ces-->

      1. In iTerm2, type: `brew update`

      2. When that finishes, type: `brew install node`

      3. Confirm `node --version` returns a version **8 or greater**.

      <!--endsec-->

      <!--sec data-title="Windows - Install Node" data-id="sectionInstallWindows" data-show=true data-collapse=true ces-->

      1. [Download](https://nodejs.org/en/) the **Current** installer for Windows [v.8.4.0].

      2. Double-click on the downloaded file & follow the installation prompts.

      3. When that finishes, confirm `node --version` returns a version **8 or greater**.

      <!--endsec-->

    2. If your version number is **8 or greater**, proceed to Step 3.

    3. If your version number is less than **8**, you'll need to update Node.

      <!--sec data-title="Mac - Update Node" data-id="sectionUpdateMac" data-show=true data-collapse=true ces-->

      1. In iTerm2, type the following: `brew update`

      2. When that finishes, type: `brew upgrade node`

      3. Confirm `node --version` returns a version **8 or greater**.

      <!--endsec-->

      <!--sec data-title="Windows - Update Node" data-id="sectionUpdateWindows" data-show=true data-collapse=true ces-->

      1. [Download](https://nodejs.org/en/) the **Current** installer for Windows [v.8.4.0].

      2. Double-click on the downloaded file & follow the installation prompts.

      3. When that finishes, confirm `node --version` returns a version **8 or greater**.

      <!--endsec-->  

3. Let's check your version of **npm** [which was installed with Node]. [_Version **5 or greater** required._]  
   In your CLI, type: `npm --version`  

   1. If your version is **5 or greater**, proceed to Part 1.

   2. If your version is less than **5**, update to the latest by typing: `npm install npm -g`

<!--sec data-title="Chromebooks Only: Cloud9 Instructions" data-id="section0" data-show=true data-collapse=true ces id="chromebook"-->

1. Sign up for an account at [c9.io](https://c9.io)

  Note: It will ask you for credit card information, but you will not get charged for anything since we do not use features of Cloud9 that cost money. Ask a mentor for the Coding & Cocktails card for Cloud9.

2. Confirm your account from your email and log in to Cloud9.

3. Select **Workspaces** from the left side panel if you are not already there.

4. Choose **Create a new workspace**.

5. Add a name for your workspace - it can be anything you like. You do not need a description, but feel free to add one if you like.

6. Leave your workspace as **Public**.

7. In the template section select the Node.js option.

8. Click on the **Create Workspace** button.

  Cloud9 will take a minute and create your workspace here.

9. We need to update the version of Node.js that Cloud9 uses by default. We'll use a tool called **Node Version Manager** to use version 8. In the terminal section of your workspace, type: `nvm use 8`

 {% hint style='tip' %}

 To make the terminal section bigger, hover over the top line of the terminal section with your mouse - it will change to an up-down arrow icon and then you can drag up which will also make the file editing area smaller.

 ![](../images/c9_terminal.png)

 {% endhint %}

10. If we leave Cloud9 and come back to this workspace, the version of Node.js resets, so let's change the default. In the terminal, type: `nvm alias default 8`

11. In the terminal, type: `npm install -g npm`  
This will ensure Cloud9 uses the most recent version of **npm**.

12. In the terminal, type `mkdir CodingAndCocktails` to create your folder/directory that you'll be working in tonight. You'll notice a new folder show up on the left side of your screen.

 {% hint style='danger' %}

 Any time the worksheet mentions to change directory to your home directory or type `cd ~` you will want to type `cd ~/workspace` instead.

 {% endhint %}

<!--endsec-->

Yay, you're done with the prep work! You're ready to proceed to Part 1.
