1. Check status
	Git status 
2. Stage (Adding)
	git add --all
	git add -A
	git add .
	git add *
	git add * .txt 
2.1 Reset
	git reset
3. Commit
git commit -m "Added Node JS notes Initial files"
	Windows:
git commit --allow-empty -n -m "Initial commit."
4. Reset Last Commit
 I ran into an error 
$ git reset HEAD~
fatal: ambiguous argument 'HEAD~': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:

got reset --hard 

5. File deletion
git rm test.txt
git rm --force test.txt
git rm --cached test.txt
git rm -r FOLDER

6. Logs
git log
git log --oneline

7. Branching
![[Pasted image 20260711160410.png| 300]]
Merged - combining the changes from two branches into one
![[Pasted image 20260711160515.png]]
git branch
git branch branchName // New branch
git checkout 

8. Merging
git merge main -m "Merging main into development"
git merge branchName

!Merge Conflict 