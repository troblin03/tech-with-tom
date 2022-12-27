# Version Control

Version control is a system that records changes to a file or set of files over time, allowing you to recall specific versions later.

###### Local Version Control Systems

Most people version control by copying files into another directory (perhaps a 'backup' folder). Whilst this is a method of version control, it is incredibly manual and error prone.

![image](https://user-images.githubusercontent.com/54938676/209634513-79d83239-a93c-418f-9935-253ba5728922.png)

To combat this, local VCSs (Version Control Systems) were developed as simple databases that kept all changes to files under revision control.

###### Centralised Version Control Systems

Local VCS is fine for an individual developer, but what happens when multiple developers need to collaborate on multiple systems? This is where Centralised VCSs were borne from.

![image](https://user-images.githubusercontent.com/54938676/209634544-afb0d66f-8202-42ea-9b90-13e80f123eb7.png)

In these systems, there is a single centralised server containing all the versioned files. The developers (or clients) can then take files from that central server.

The clear advantage to this is the easier ability to collaborate on a single project. It provides transparency over what each person is working on and easy collaboration. However, the serious downside is that this represents a _single point of failure_ with the central server being a large concern. If the server were to go down for an hour then you lose absolutely everything. Whenever you have the entire history of one project in a single place, you risk losing everything.

###### Distributed Version Control Systems

The disadvantage above is what Distributed VCSs were innovated to combat. These are now common best practice, with Git being the most commonly used.

Rather than clients removing snapshots of files one at a time, they fully 'mirror' the repository (or version database). As a result, if any server dies only localised changes will be lost because the most recent previous version can be copied back up to the server to restore it. In other words, every clone is really a full backup of all the data.

![image](https://user-images.githubusercontent.com/54938676/209635799-c8c00006-97d9-4d86-af36-2c9d93be5ea7.png)

## Resources

https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control
