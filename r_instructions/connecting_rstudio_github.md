Connecting RStudio to a GitHub Repository
================
Carson McKee
2024-04-22

Here we will look at how to create a local git repository (repo) and
connect it to an RStudio project.

# Prerequisites

If you have not already done so, read the ‘Creating a Local Git
Repository with RStudio’ and create a (free) GitHub account here
<https://github.com/>. Note that GitHub accounts are usually shared with
others and on CV’s, so choose a username that you are happy to share
with others.

# Create a GitHub Repo

If starting an entirely new project, we must first create the GitHub
repo on the website. After logging into your GitHub account, navigate to
‘Repositories-\>New’ which will take you to the page below.
![](github_images/github_1.png) After choosing a repository name
selecting ‘Create repository’, your empty repo (except perhaps for a
README file) will appear as below.

![](github_images/github_2.png)

# Cloning a GitHub Repo with RStudio

Now in order to link and clone a GitHub repo to RStudio we first
navigate to the repo on GitHub and select the ‘Code’ drop down (see
below). Here you will be presented with an HTTPS link which you should
copy. ![](github_images/github_3.png) We now move back to RStudio and
got to ‘File-\>New Project-\>Version Control-\>Git’ (see below)

![](github_images/github_4.png)

![](github_images/github_5.png)

Now simply paste the HTTPS link we copied from GitHub into the
Repository URL field and select ‘Create Project’.

![](github_images/github_6.png)

After buffering, RStudio will open a new project and you should see the
files from the GitHub repo appear in the files and git tabs.

![](github_images/github_7.png)

# Inviting Collaborators

Before others can begin to commit/push code to your GitHub repo, you
must invite them as collaborators. To do this, go to your repository
page on the GitHub website and navigate to ‘Settings-\>Collaborators’.
![](github_images/add_collab_1.png)

GitHub may then prompt you to do 2-factor authentication. After this you
will see the option to add collaborators. Now just enter the email
address to their GitHub and ensure you give them both read and write
access. GitHub will then send them an invite.

![](github_images/add_collab_2.png)

If the collaborators are using RStudio, then they should now follow the
steps in section 3 for cloning the repo.

# Keeping Your Local Repo Up to Date (Pulling)

Now that you have cloned the repo and invited others to collaborate,
modifying, committing, branching and merging files is the same as when
using git locally. However, because we are sharing the repo with others
through GitHub, it is possible that the cloned repo becomes out of sync
with the GitHub repo due to others making changes. If you make local
commits on an out of date version of the repo and then try to push your
changes to GitHub, you may cause a conflict (see later section). In this
case git will insist that you make your repo up to date before
incorporating your changes. This is known as ‘Pulling’ - which is
essentially just syncing your local repo with the GitHub repo. You
should do this often to ensure your local repo is up to date. For
example, in the test repo I created in the previous section, I have
added an R file on GitHub (see below). ![](github_images/github_8.png)
Because this file was created and committed directly on GitHub, it won’t
appear in my cloned repo unless I do a Pull. To do this, simply click on
the ‘Pull’ button in the ‘Git’ tab of RStudio. This will then sync with
GitHub and notify you of any changes that have been made to you local
repo. In my case, ‘main.R’ will now appear in my files.
![](github_images/github_9.png) ![](github_images/github_10.png)

# Adding Changes to the Shared Repo (Pushing)

Once you have Pulled from GitHub and committed your changes, you must
now ‘Push’ your changes. This uploads any changes made locally to the
GitHub repo so that others can pick them up when they make a Pull
request. To Push, simply select the ‘Push’ button in the Git panel.
![](github_images/github_11.png)

# Dealing with Conflicts (Merging)

Merge conflicts usually occur when you want to push changes you have
made locally to GitHub but your local repo has become out of sync. This
means that there are commits present on GitHub which are not present on
your local repo. In this case git will insist that you do first make a
Pull request to merge your changes with those already on GitHub. In some
cases merging these conflicts is easy and git will do it for you. For
example, if the only differences are a collection of completely new
files, then there is no issue because they can’t possibly affect
anything. Or if the code you are changing is completely separate from
the changes on GitHub, then git may also merge this automatically.
However, in some cases it may be that your changes are relying on code
that has been removed on GitHub. In cases like this, there is no one way
to fix the problem and it must be treated on a case by case basis.
Generally, you want to first incorporate any changes that have been made
on GitHub, then begin to modify your changes to work on top of this.

# Some things to try

1.  Create a GitHub repo and invite some of the people around you as
    collaborators.
2.  Have a go at Pulling/Pushing your own files to the GitHub repo.
3.  Each try to Push your changes to the same file at the same time.
    This should create merge conflicts which you will need to resolve.
4.  Try creating and working on your own branches and then merging again
    with the master branch.
