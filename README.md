# 4-7-raspberry-pi-python-execution-v2

[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=21742070)
# Overview

Python scripts can run on the Raspberry Pi Operating System (which is a type of Linux operating system). In previous assignments, you have set up your Raspberry Pi and made sure that you can connect to the pi on your computer using an SSH command in PowerShell or Mac Terminal.

In this assignment, you will learn how to write code on your computer in GitHub and transfer the code to run directly on the Raspberry Pi using the SSH protocol. This will involve the following parts:

1. Write the code in GitHub Codespaces (VS Code in the cloud)
2. Test the code on GitHub Codespaces
3. Push the code to your GitHub repository
4. Use SSH to connect your computer to your Raspberry Pi
5. Use SSH to connect your Raspberry Pi to GitHub
6. Clone (download) the code from the GitHub repository to the Raspberry Pi using SSH
7. Test the code on the Raspberry Pi

# Writing the Code on the Raspberry Pi

## Part 1: Write the code in GitHub Codespaces (VS Code in the cloud)

Before you play the video, click on the video settings icon in the bottom right corner and increase the video quality so you can read the words on the screen.

We are going to walk through step by step how to write code on your raspberry pi. Just like your previous assignments involving the Raspberry Pi, you will need to be on campus in order to successfully complete steps 4 and 5 above.

- Step 1: [Accept the assignment](https://classroom.github.com/a/WWPFtbPb).
- Step 2: Click the Open in GitHub Codespaces button.
- Step 3: You need to create a new file. To create a new file either right-click in the empty space in the left panel and click New File or click the New File button next to the assignment title. 
- Step 4: Title your new file "app.py". This file will be used to test that you can make a simple program to run on the Raspberry Pi.
- Step 5: The new file will open in the editor in a new tab called app.py. Write a print statement that says, "Hello [your name]" in the app.py file. For example, if your name was Michael, you would write a print like this: `Print("Hello Michael.")`


## Part 2: Test the code on GitHub Codespaces
- Step 1: Run the program in the Codespace to be sure it works. To run your code, simply click the play button in the top right of your Codespaces window. 
     - Note: testing pieces of the project early and often will help you later in case you need to troubleshoot. For example, let's assume you get to the end of this assignment, and your code is not running on your Raspberry Pi. If you have already tested your code in Codespaces, you know that the problem is coming from one of the steps after this one. Taking time to test your code as you go is always worth it.
- Step 2: You will know if your code works if you see your message appear in the Codespaces terminal.

## Part 3: Push (upload) the code to GitHub
- Step 1: Push the code to GitHub using the Source Control button on the left panel.
- Step 2: Add a commit message that describes the change you made. In this case, since you changed your name, you might write "Changed name to [Your Name]." 
- Step 3: Click Commit
- Step 4: Codespaces will now ask you a series of questions. To make everything work properly, select the following options: 
    - In the center of your screen you will see a message that says, "There are no staged changes to commit. Would you like to stage all your changes and commit them directly?" Click Always - you can think of this like putting some items in a box you are about to ship. We call it staging because we are preparing the files before we commit (upload) the code.
    - On the left panel, where you clicked Commit before, you will now see an option to sync changes. Click Sync Changes - this means push (upload) and pull (download) the latest changes you've made to your GitHub repository or project:
    - In the center of your screen you will see a message that says,  "This action will pull and push commits from and to "origin/main"." Click OK, Don't Show Again - see previous step explanation
    - In the bottom right corner, you will see a message asking you if you would like VS code to periodically run "git fetch." Click No - this will allow you to choose when you want to pull (download) code changes
    - Your code has now been pushed (uploaded) to GitHub! That's how we share code with our co-workers in real programming teams.
Next, we will copy the program to the Raspberry Pi. Important: you must be on campus to finish this assignment. Your computer and pi must be connected to the same network: ensign-tech-lab

## Part 4: Use SSH to connect your Raspberry Pi to your computer ***and*** to GitHub
**Important:** you must be on campus to finish this assignmnet. Your computer and pi must be connected to the same network: ensign-tech-lab\

The way you run commands directly on the raspberry pi is by using SSH. You need to use an SSH to connect your pi to your computer and to connect your pi to GitHub. Fortunately, you already know how to use SSH to connect your computer to your Raspberry Pi, so these first few steps will be very easy.

- Step 1: Plug in the Raspberry Pi, and turn it on. Be sure the green light is on. Wait 5 minutes while the pi starts up completely.
- Step 2: Open PowerShell (Windows) or Mac Terminal (Apple) on your computer
Open PowerShell by typing Power in the Windows search bar and clicking PowerShell
- Step 3: Write an SSH command to connect to the Raspberry Pi. If you need to remember how to write that command, you can reference the Raspberry Pi Set-Up assignment. If your pi has connected successfully, you will see the green text with the name of your Raspberry Pi.

To connect your Raspberry Pi to GitHub, you need to generate a public key on your Pi. This key is required for secure connections to GitHub. Unlike your personal computer, GitHub is a shared platform, so it uses public keys to ensure only authorized users can access and modify code, protecting project integrity and security.

- Step 4: To generate an SSH public key for your Raspberry Pi, type the command ssh-keygen in your terminal.
- Step 5: After typing the command, hit enter 4 times.
- Step 6: Display the public key in your terminal by typing the command: `cat ~/.ssh/id_rsa.pub`
    - In coding, displaying information in your terminal is often called printing.
    - You need to display the information so you can copy it to GitHub

The next few steps are adapted from the GitHub article [Adding a New SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

- Step 7: Copy all of the information printed (including ssh-rsa)
- Step 8: Open [GitHub](https://github.com) and log in to your account. 
- Step 9: In the upper-right corner of any page, click your profile photo, then click Settings.
- Step 10: In the "Access" section of the sidebar, click SSH and GPG keys.
- Step 11: Click New SSH key or Add SSH key.
- Step 12: In the "Title" field, add a descriptive label for the new key.
    - For example, since you are adding a Raspberry Pi, you might call this key "Raspberry Pi-XX," where the XX is replaced by your Raspberry Pi number listed on the case.
- Step 13: Leave the key type as Authentication, which means it's for automating logging in to GitHub.
- Step 14: In the "Key" field, paste your public key.
- Step 15: Click Add SSH key.
- Step 16: If prompted, confirm access to your account on GitHub.

## Part 5: Clone (download) the code from the GitHub repository to the Raspberry Pi
With the SSH connection created between your pi and GitHub, you can now copy the program from Codespaces to the Raspberry Pi.
- Step 1: Click the [assignment link](https://classroom.github.com/a/WWPFtbPb). This is the same link from Part 1, Step 1.
- Step 2: Click the blue link to your GitHub repository
- Step 3: Click the green Code button
- Step 4: Click the Local tab, and then the SSH tab
- Step 5: Copy the url

## Part 6: Test the code on the Raspberry Pi (back in PowerShell/Mac Terminal)
- Step 1: Back in your PowerShell or Mac Terminal type the following command: git clone [URI] . Replace [URI] with the URI you copied from the previous step.
- Step 2: Type the command cd ./1-10* This takes you to the directory where the code was downloaded so you can run the program you created.   
- Step 3: Now you are going to run the code you wrote in Part 1. To do this, type the command: python app.py . This is the name of your program. 
- Step 4: You will see "Hello [Your Name]" appear on your screen in the PowerShell or Mac Terminal.
- Step 5: Take a screenshot of the terminal with your message.

Excellent work! You have run your first program on your pi.

## Submission

Submit your screenshot of the terminal in Canvas.

s part of this assignment you pushed (uploaded) your code to GitHub in this repository. If you need a refresher on how to submit code to GitHub, you can look at the How to Submit Labs page on Canvas.

