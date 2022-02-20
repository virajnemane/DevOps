# Before doing anything lets understand how GIT works.
1) we create repo on github.com
2) we clone it on our system. this is called local repository.
So now we have 2 repository, one Remote repository (created on github.com), and another one is local repository (which is on our system.)
3) we create file in workspace. Workspace is different than local repository.
4) we add newly created file in index. Index is db, list of files tracked by git for any changes, which contains detail about changes in local repository.
Note - Only newly created file need to add in index.
5) we execute commit command, which submit changes done in workspace to local repository.
6) we execute push command which push changes from local repository to remote repository.

## Create git account on github.com

## Create git repo name as "myfirstrepo"

## install git on server
	yum install git -y

---------------------
## clone git repo on server/local system
	git clone https://github.com/indorenilesh/myfirstrepo.git

## create test file inside repo and check status
	cd myfirstrepo

#### create test.txt and add below line
	This is my first edit.

#### check git status
	git status

#### add new file in index
	git add test.txt
	git status

#### commit file in local repo
	git commit -m "first edit"
	git status

#### push changes to github
	git push

#### Open test.txt file in github make changes and save/commit it.
	This is my second edit.

#### pull repo to get latest update.
	git pull

#### edit test.txt file again and add 3rd line
	cd myfirstrepo

	vim test.txt
		This is my third edit.
	git status
	git add test.txt
	git status
	git commit -m "third edit"
	git status
	git push

## Now I want a older version of file.
#### check git log for older versions of file
	git log --oneline

## select version id and restore it
	git checkout <versionid> test.txt
	git status
	git add test.txt
	git status
	git commit -m "restoring older version file"
	git status
	git push

-----------------
## how to upload your existing project on git 
#### create directory and inside that directory
	mkdir mysecondrepo
	cd mysecondrepo
	git init

#### create some file then add and commit those files locally
	vim test.txt
		This is my first edit.
	git add test.txt
	git commit -m "uploading first file"
 
#### create git repo on github.com

#### inform local git about remote git
	git remote add origin https://github.com/indorenilesh/mysecondrepo.git

#### push files to remote git
	git push

----------------
## difference between git fetch and git pull
1) create new file add one line in file.
2) push change to git
3) edit file add second line in remote repository
4) do git fetch - will fetch changes
5) check file in workspace - no changes
6) do git pull 
7) check file in workspace - you will get new changes.

![](/LearnGIT/image/fetch-vs-pull.png)

------------
## Bottom line
1) git fetch - fetches update from remote repository to local repository
2) git pull - pulls updates from remote repository to local repository as well as workspace directly.
3) before commiting workspace changes, do git fetch to know that, is there any changes done in orignal(remote) repository.
This will help not to loose workspace changes.