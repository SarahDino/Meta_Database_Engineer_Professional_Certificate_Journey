Step 1: Create a new repository on your Github account named "repo-exercise". Ensure that "Add a README file" is selected.


Step 2: Open the Terminal and authenticate using gh (Github CLI):
"gh auth login"


Step 3: Create an authentication token in your Github account with specified scopes given in the terminal. Copy it from Github and paste it. Verify authorization was successful.


Step 4: Clone the repository using its GitHub CLI.
"gh repo clone <YOUR USERNAME>/<REPOSITORY-NAME> " <br>
![seconde Lab](secondeLab1.PNG)


Step 5: Move to the repo directory by using "cd <REPOSITORY-NAME>"<br>
![seconde Lab](secondeLab2.PNG)

Step 6: add the"result.txt" to the repository folder on your local machine<br>
![seconde Lab](secondeLab3.PNG)


Step 7: In the Git terminal, run the "git status" command.



Step 8: Verify that the output shows "result.txt" as an untracked file.<br>
![seconde Lab](secondeLab4.PNG)


Step 9: Run the command "git add result.txt"<br>
![seconde Lab](secondeLab5.PNG)


Step 10: Run the "git status" command again.


Step 11: Verify that the output shows "result.txt" as a tracked file.<br>
![seconde Lab](secondeLab6.PNG)


Step 12: Next, run the "git commit" command and specify the commit message as "Successful exercise"<br>
![seconde Lab](secondeLab7.PNG)


Step 13: Next, run the "git push" command.<br>
![seconde Lab](secondeLab8.PNG)


Step 14:  On Github, go to your repository page. Verify that the "result.txt" file is listed. You may need to refresh the page to see the changes. <br>
![seconde Lab](secondeLab9.PNG)


