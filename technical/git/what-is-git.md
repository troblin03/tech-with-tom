# A brief background of Git

Git differentiates itself from othe VCSs because it thinks about its data as a series of snapshots of a smaller file system. Other VSCs will commonly refer to themselves as _delta-based_ version control. That is, they store changes made to each file over time.

The way these 'snapshots' work is that when something is pushed to your Git repo, Git will take a picture of all of the files and what they look like in a given moment. From this picture, Git will ignore any files that are untouched whilst storing reference to changed files. This way, you have an understanding of the way an entire file system looked at any given moment.

![image](https://user-images.githubusercontent.com/54938676/209637368-dae80362-8aa9-4753-81fa-ba3300a4afc4.png)

Another advantage of Git is its ability to run almost every operation _locally_. This means that Git isn't constantly retrieving information from a server to return to the client. For example, if you want to understand the changes between a file a month ago to now, Git can do a local difference calculation much faster than if fetching information from a server was required.

## The three states

Within Git, there are three primary states that files can reside in:

- **Modified -** You have changed the file but not yet committed it to your database.
- **Staged -** A modified file has been marked to go into the next commit snapshot.
- **Committed -** The data is safely stored in your local Git database

Whilst these are the three main _states_ that a file can reside in. There are also three main _sections_ of a Git project.

- **Working Directory -** On a particular client, is a single checkout of one version of the project. The files are pulle out of the compressed database and placed on the disk for the user to modify.
- **Staging Area -** A file generally contained in the Git directory that stores information about what will appear in the next commit
- **Git Directory -** Where Git stores the metadata and object database for a project. This is what is copied when a repository is cloned.

The workflow through these stages is:

1. You 'clone' or checkout the project from Git into a local working directory where you modify files as needed
2. You selectively stahe those changes that will be part of the next commit, adding only those changes to the staging area.
3. You initiate a commit, taking the files in the staging area and storing the snapshot permanently in your Git directory.

![image](https://user-images.githubusercontent.com/54938676/209639136-ad0e800a-bba9-4d13-91c4-d1a6b957ddc5.png)

## Resources

https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
