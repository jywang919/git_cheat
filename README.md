# git_cheat

-------force overwrite local
git reset --hard HEAD
git clean -f -d -n
git pull

------ UI commit work around
in eclipse -> git staging -> commit
in cmd -> git push


============================= Git  -- https://www.youtube.com/watch?v=1tC6Z57AOkY
git config --list

git config --global core.editot nano.exe

-------list remote origin
	git remote -v

	git init 
	git remote add origin  <the url>

------- list untracked files

	git status

------ stage
	git add .  (or git add jw123.txt)	

-----  commit
	git commit -m 'Jw 1st commit'

----  push
	git push -u -f origin master

--------------- Branches
		-- list local branches
		-- git branch -r 
	------------- check/create a branch
		git branch 'test_branch'
		git checkout -b branch-1
		--- list the branch
			git branch -vv

		--  git push --set-upstream origin 'test_branch'

	 ------- switch branch
	 	git checkout master		

	-------------- create branch on bitbucker then fetch to local
	git fetch --all

	--------- delete branch
		delete local
		1.	git checkout master
		2.	git branch -d 'test_branch'

		delete remote
		git push -d origin branch_from_bitbucket

   -------------- Merge 1-2-3 
   create source at master - 
   git checkout branch-1
   make change by branch-1
   		git add -> commit -> git push --set-upstream origin branch-1
	
   git checkout branch-2
   make change by branch-2
   		git add -> commit -> git push --set-upstream origin branch-2

   ----------
   git checkout master
   git merge branch-1
   		git push 
   git merge branch-2
   		==> conflict
   			resolve conflict in Visual Code Ctl-Shift-F to search for <<<<
   			save -> git add -> commit -> push
   	check bitbucket  -> commit to see graph

   	----- Git Revert
   		at master
   		1. bad code change
   		2. git add -> commit -m "bad commit" -> push
   		---- 
   		git log --oneline --> get the commit ID
   		git revert dd624a1
   		git add commit push

   ------ git stash -- store work before going to another branch (otherwise commit push is needed)
   	list
   	apply -- last element in stash
   	clear
	
	git add .
	git stash save
	git stash
	git stash list -- gto get stash number

	git stash apply  <the stash number>

	------ gitignore git status won't list ingore files 
		*.class
		target/
		secret.html


