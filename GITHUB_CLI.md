# Github Cheatsheet for command line
</br>

-------------------------------------------
* Items contained in [ ] are optional and all caps words should be replaced, except "HEAD".
-------------------------------------------
</br>

### Just installed Git ?

	git config --global user.name "Your Name" 
	git config --global user.email "your@email.com" 
	git config --global color.ui true 
	git config --global core.autocrlf true
</br>

### Create

- From existing data

		git init 
		git add . 
		git commit -m "Initial commit." 

- From existing repo 

		git clone ~/existing ~/new 
		git clone https://USER@HOST.COM/PROJECT.git
</br>

### Browse

- View changed files 

		git status 

- View changes 

		git diff [ID:FILE] 

- View changes between commits 

		git diff ID1 ID2 

- View History 

		git log 

- Who did this? 

		git blame FILE 

- View changes between branches 

		git diff branch1..branch2 

- View changed files between branches 

		git diff --name-status branch1..branch2
</br>

### Update

	git fetch [REMOTE BRANCH]
</br>

### Fetch and merge 

	git pull [REMOTE BRANCH]
</br>

### Local work

- Add all changes to stage 

		git add . 

- Commit all tracked files 

		git commit -a [-m "Initial commit."] 

- Commit staged changes 

		git commit 

- Unstage file 

		git reset FILE
</br>

### Branch

- View branches 

		git branch

- Create branch off current 

		git branch BRANCH 
		git checkout -b BRANCH 

- Switch between branches 

		git checkout BRANCH 

- Merge branches 

		git checkout BRANCH2 

- Delete local branch 

		git branch -d BRANCH 

- Delete without merging

		git branch -D BRANCH 

- Delete remote branch 

		git push REMOTE --delete BRANCH 

- Fetch remote branch to local 

		git pull REMOTE REMOTE_BRANCH:LOCAL_BRANCH
</br>

### Stash

- Save a stash 

		git stash 

- View stashes 

		git stash list 

- Apply stash 

		git stash apply [STASH1] 

- Apply and remove

		git stash pop 

- Clear all stashes 

		git stash clear
</br>

### Reset

- Revert to last commit 

		git reset --hard HEAD^ 

- Undo last commit 

		git reset --soft HEAD^ 

- Reset file 

		git checkout -- FILE
</br>

### Publish

- Push changes to another repo 

		git push [REMOTE BRANCH] 

- Make a version or milestone 

		git tag NAME 
</br>

### Maintenance

- Remove untracked files and directories 

		git clean -fd 

- Check for errors

		git fsck
</br>

### Aliases

- Config format 

		git config --global alias.co "checkout" co "checkout" st "status -sb" ls "log --pretty=format:'%h: %s'" df "diff" ci "commit" 

- Usage 

		git co branch
</br>

### Archive

- Archive into a zip file

		git archive --format zip --output /full/path/file.zip BRANCH
</br>

### Advanced

- Amend commit

		git commit -m "Initial commit." 
		git add FILE 
		git commit --amend

- Push to a different remote branch

		git push REMOTE LOCAL_BRANCH:REMOTE_BRANCH

- Access new remote branch

		git fetch REMOTE REMOTE_BRANCH:LOCAL_BRANCH 
		git checkout LOCAL_BRANCH

- Set upstream

		git branch --set-upstream BRANCH REMOTE/REMOTE_BRANCH
</br>

### Files

- Untrack file without removing 

		git rm --cached FILE 

- Untrack folder without removing 

		git rm -r --cached FOLDER/. 
</br>

### Changes

-  Ignore file mode changes 

		git config core.fileMode false 

- Force Overwrite of Local Files

		git fetch --all 
		git reset --hard REMOTE/BRANCH
