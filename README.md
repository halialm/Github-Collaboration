# GitHub Collaboration Exercise: Your First Collaborative Project
This exercise will guide you through the fundamental steps of collaborating on a project using GitHub. You'll learn about branches, merging, and how to resolve potential merge conflicts, giving you a practical foundation for your first collaborative project.

1. Prerequisites
Before you start, make sure you have:

- A [GitHub.zhaw.com](https://github.zhaw.ch/) account (since you made it here, you probably have that sorted.).
- Git installed on your local machine.
- Visual Studio Code (VS Code) installed 

3. Core Concepts

- Repository (Repo): A project's folder where all files, folders, and the history of changes are stored.

- Forking: Creating a personal copy of someone else's GitHub repository under your own account. This allows you to freely make changes without affecting the original project.

- Cloning: Creating a local copy of a remote GitHub repository (your forked copy) on your computer.

- Branch: An independent line of development. You create branches to work on new features or bug fixes without affecting the main project until your work is ready. The main (or master) branch is usually the stable version of the project.

- Commit: A snapshot of your changes at a specific point in time. Each commit has a unique ID and a message describing the changes.

- Pushing: Uploading your local commits to the remote GitHub repository (your forked copy).

- Pulling: Downloading changes from the remote GitHub repository to your local machine.

- Pull Request (PR): A way to propose changes from your branch to another branch (e.g., from your feature branch to main). It's a formal request for others to review and merge your code.

- Merging: Combining the changes from one branch into another.

- Merge Conflict: Occurs when two or more people have made conflicting changes to the same lines of code in the same file.

4. The Collaboration Exercise
Let's simulate a collaborative project with 3 collaborators.

Scenario: Building a Simple "About Us" Page
Imagine you and two partners are creating a simple HTML "About Us" page.

Step 1: Person A - Fork this Pre-made Exercise Repository.

Instead of creating a new repository, you will start by forking an existing template. This template will contain the `index.html` file we'll be working on.

Fork the repository: In the top right corner of the template repository page, click the Fork button.

Create your fork: You'll be prompted to create a new fork.

Under "Owner," ensure your GitHub username is selected.

You can keep the repository name as is (e.g., github-exercise-template) or rename it (e.g., my-about-us-page).

Click Create fork.

You now have your own copy of the template repository under your GitHub account! This will be your primary repository for this exercise.

Invite your partners (One person, the "Project Initiator", does this): If you are working with partners, one of you should act as the "Project Initiator" and invite the others as collaborators to your forked repository.

Go to your forked repository on GitHub.

Go to Settings -> Manage Access -> Invite a collaborator and add each of your partners' GitHub usernames.

Your partners should accept the invitations.

Step 2: Clone Your Forked Repository to your Local Machine (All partners do this)

On GitHub, navigate to your forked copy of the repository (e.g., https://github.com/your-username/github-exercise-template).

Click the Code button (green button).

Copy the HTTPS URL.

Open your VS Code and press `CTRL + Shift + P ` and enter `git clone`
- Paste the url from the reposory
Navigate to the directory where you want to store your projects.
- directly open your cloned repository

Step 3: Create and Switch to a New Branch (Each partner creates their own branch)

- Partner A: Will add a section for "Our Mission".

- Partner B: Will add a section for "Our Vision".

- Partner C: Will add a section for "Our Values".

Partner A:

Open the VS Code command menu (same as for git clone) and select `git checkout` feature/our-mission

This command creates a new branch named feature/our-mission and switches you to it.

Partner B:

Open the VS Code command menu (same as for git clone) and select `git checkout`  feature/our-vision

This command creates a new branch named feature/our-vision and switches you to it.

Partner C:

Open the VS Code command menu (same as for git clone) and select `git checkout` feature/our-values

This command creates a new branch named feature/our-values and switches you to it.

Open the index.html file in your preferred code editor (VS Code is highly recommended).

Partner A: Add the following section before the closing

```
</body> tag:
<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

    <h2>Our Mission</h2>
    <p>To empower learners with practical collaboration skills through real-world projects.</p>
</body>
```

Partner B: Add the following section before the closing </body> tag (but assume Partner A and C haven't pushed their changes yet):
```
<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

    <h2>Our Vision</h2>
    <p>To foster a global community of innovators working together seamlessly.</p>
</body>
```

Partner C: Add the following section before the closing </body> tag (but assume Partner A and B haven't pushed their changes yet):
```
<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

    <h2>Our Values</h2>
    <p>Integrity, Innovation, and Inclusivity are our core principles.</p>
</body>
```

Save the index.html file after making your changes.

Step 5: Commit and Push Your Changes

Each partner now commits and pushes their changes to their own branch on GitHub. Follow the manual that has ben shared with you on moodle.

tep 6: Create a Pull Request (PR) and Merge in Sequence

After pushing, go to GitHub. You'll likely see a banner suggesting you create a pull request. The order of merging is crucial here to experience conflicts.

Partner A (First to Merge):

Go to your forked repository on GitHub.

Click Compare & pull request next to your feature/our-mission branch.

Ensure the base branch is main and the compare branch is feature/our-mission.

Give your PR a clear title (e.g., "Add Our Mission section").

Add a description if needed.

Click Create pull request.

Now, click Merge pull request and Confirm merge.

Then, you can click Delete branch.

Partner B (Second - Will Encounter Conflict):

Go to your forked repository on GitHub.

Click Compare & pull request next to your feature/our-vision branch.

Ensure the base branch is main and the compare branch is feature/our-vision.

Give your PR a clear title (e.g., "Add Our Vision section").

Add a description if needed.

Click Create pull request.

Now, you will see a message: "This branch has conflicts that must be resolved." Do NOT merge yet. Proceed to Step 7.

Partner C (Third - Will Encounter Conflict):

Go to your forked repository on GitHub.

Click Compare & pull request next to your feature/our-values branch.

Ensure the base branch is main and the compare branch is feature/our-values.

Give your PR a clear title (e.g., "Add Our Values section").

Add a description if needed.

Click Create pull request.

Now, you will also see a message: "This branch has conflicts that must be resolved." Do NOT merge yet. Proceed to Step 7.

Step 7: Resolve the Merge Conflicts (Partner B then Partner C does this)

Since Partner A's changes are now on main, and Partner B's and C's changes conflict with main, Partner B and C need to resolve this locally.

Partner B (on your local machine - Resolve First):

Switch back to your main branch:

git checkout main

Pull the latest changes from GitHub's main branch (this brings in Partner A's "Our Mission" section):

git pull origin main

Now, switch back to your feature branch:

git checkout feature/our-vision

Merge the main branch into your feature branch:

git merge main

Git will now notify you of a merge conflict. Open your index.html file in VS Code. You will see conflict markers:

```
<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

<<<<<<< HEAD
    <h2>Our Vision</h2>
    <p>To foster a global community of innovators working together seamlessly.</p>
=======
    <h2>Our Mission</h2>
    <p>To empower learners with practical collaboration skills through real-world projects.</p>
>>>>>>> main
</body>
```

`<<<<<<< HEAD`: Marks the beginning of the conflicting changes from your current branch (feature/our-vision).

 `=======`: Separates the changes from your branch and the incoming changes.

`>>>>>>> main`: Marks the end of the incoming changes from the main branch.

To resolve the conflict using VS Code:

When you open index.html in VS Code, it will automatically detect the merge conflict.

You'll see options like "Accept Current Change," "Accept Incoming Change," "Accept Both Changes," and "Compare Changes."

Choose "Accept Both Changes" to keep both "Our Mission" and "Our Vision" sections. VS Code will automatically clean up the conflict markers.

Alternatively, you can manually edit the file to include both sections, removing the conflict markers, as shown below:

<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

    <h2>Our Mission</h2>
    <p>To empower learners with practical collaboration skills through real-world projects.</p>

    <h2>Our Vision</h2>
    <p>To foster a global community of innovators working together seamlessly.</p>
</body>

Save the index.html file.

Stage the resolved file:

git add index.html

Commit the merge resolution (Git will provide a default message, you can accept it or change it):

git commit -m "Resolve merge conflict: Added Our Mission and Our Vision sections"

Push your updated feature branch to GitHub:

git push origin feature/our-vision

Partner B (on GitHub - Complete Merge):

Go back to your Pull Request on GitHub.

The "This branch has conflicts..." message should now be gone.

Click Merge pull request and Confirm merge.

Then, you can click Delete branch.

Partner C (on your local machine - Resolve Second):

Switch back to your main branch:

git checkout main

Pull the latest changes from GitHub's main branch (this now brings in both Partner A's "Our Mission" AND Partner B's "Our Vision" sections):

git pull origin main

Now, switch back to your feature branch:

git checkout feature/our-values

Merge the main branch into your feature branch:

git merge main

Git will now notify you of another merge conflict. Open your index.html file in VS Code. You will see conflict markers, but this time they will include changes from both previous merges.

<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

<<<<<<< HEAD
    <h2>Our Values</h2>
    <p>Integrity, Innovation, and Inclusivity are our core principles.</p>
=======
    <h2>Our Mission</h2>
    <p>To empower learners with practical collaboration skills through real-world projects.</p>

    <h2>Our Vision</h2>
    <p>To foster a global community of innovators working together seamlessly.</p>
>>>>>>> main
</body>

To resolve the conflict using VS Code:

Choose "Accept Both Changes" to keep your "Our Values" section and the incoming "Our Mission" and "Our Vision" sections.

Manually arrange them in the desired order (e.g., Mission, Vision, Values):

<body>
    <h1>Welcome to Our Team!</h1>
    <p>This is the initial version of our About Us page.</p>

    <h2>Our Mission</h2>
    <p>To empower learners with practical collaboration skills through real-world projects.</p>

    <h2>Our Vision</h2>
    <p>To foster a global community of innovators working together seamlessly.</p>

    <h2>Our Values</h2>
    <p>Integrity, Innovation, and Inclusivity are our core principles.</p>
</body>

Save the index.html file.

Stage the resolved file:

git add index.html

Commit the merge resolution:

git commit -m "Resolve merge conflict: Added Our Values, Mission, and Vision sections"

Push your updated feature branch to GitHub:

git push origin feature/our-values

Partner C (on GitHub - Complete Merge):

Go back to your Pull Request on GitHub.

The "This branch has conflicts..." message should now be gone.

Click Merge pull request and Confirm merge.

Then, you can click Delete branch.

Step 8: Final Check (All partners)

On your local machine, switch back to main:

git checkout main

Pull the latest changes from GitHub:

git pull origin main

Now your local main branch should reflect all merged changes from Partner A, B, and C.

Open index.html locally to see the combined content.

5. Tips for Effective Collaboration
Pull Frequently: Always git pull origin main (or master) on your main branch before creating a new feature branch and regularly pull changes from the main branch into your feature branch to stay updated and minimize conflicts.

Small, Frequent Commits: Make small, logical commits with clear messages. This makes it easier to track changes and debug.

Descriptive Branch Names: Use names that indicate the purpose of the branch (e.g., feature/add-login, bugfix/fix-homepage-typo).

Clear Pull Requests: Write detailed PR descriptions explaining what you did, why, and any relevant context.

Review Code: Always review your teammates' PRs and provide constructive feedback.

Communicate: Talk to your team! Let them know what you're working on to avoid simultaneous edits on the same files.