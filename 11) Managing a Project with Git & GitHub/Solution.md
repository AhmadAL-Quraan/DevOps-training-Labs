* [[#Phase 1 Project Setup]]
* [[#Phase 2 Viewing Project History]]
* [[#Phase 3 Working with Branches]]
* [[#Phase 4 Discarding Changes]]
* [[#Phase 5 Pull Request]]
* [[#Phase 6 Creating a Conflict]]
* [[#Phase 7 Searching the Repository]]
* [[#Phase 8 Inspecting Changes]]
* [[#Phase 9 Undoing Commits]]



---


## Phase 1: Project Setup

1) Create the repo 
![[swappy-20260108-163346.png]]

2) Copy the repository to your local machine.
```bash
git clone git@github.com:AhmadAL-Quraan/Github-task.git
```
![[swappy-20260108-163406.png]]
 

3) Create a text file named notes.txt and write at least one line of text in it.

```bash
cd Github-task
echo "HI" > notes.txt
```

 ![[Pasted image 20260108164001.png]]

4) Check the repository status and verify that the new file is detected.
```bash
git status
```
![[Pasted image 20260108164044.png]]

5) Save the initial changes to the repository and upload them to GitHub.
```bash
git add .
git commit -m "Done"
git push -u origin main
```
 ![[Pasted image 20260108164143.png]]




---


## Phase 2: Viewing Project History

1) Display the full history of saved changes in the repository.
```bash
git log
```

![[Pasted image 20260108164336.png]]

2) Display a shortened version of the history showing one entry per change.
```bash
git log --oneline
```

![[Pasted image 20260108164438.png]]



---


## Phase 3: Working with Branches

1) Create a new branch for feature development and switch into it
```bash
git checkout -b "dev"
```
![[Pasted image 20260108164556.png]]

2) Edit the notes.txt file by adding a new line that 
![[Pasted image 20260108164718.png]]

3) Compare the current version of the file with the last saved version (last commited one).
```bash
git diff notes.txt
```
![[Pasted image 20260108164915.png]]
4) Save the changes in the feature branch && upload the feature branch to github.
```bash
git add . 
git commit -m "Feature branch started"
git push -u origin dev
```
![[Pasted image 20260108165013.png]]


---

## Phase 4: Discarding Changes

1) Modify the notes.txt file again without saving the change to the repository.
![[Pasted image 20260108165223.png]]

2) View the difference between the modified file and the saved version.
```bash
git diff notes.txt
```
![[Pasted image 20260108165259.png]]

3) Discard the latest change and restore the file to its last saved state.
```bash
git restore notes.txt
```
![[Pasted image 20260108165351.png]]

4) Confirm that the repository has no pending 
```bash
git status
```
![[Pasted image 20260108165502.png]]




---



## Phase 5: Pull Request


1) On GitHub, create a Pull Request to merge the feature branch into the main branch.
![[Pasted image 20260108165900.png]]![[Pasted image 20260108165912.png]]
![[Pasted image 20260108165931.png]]





---


## Phase 6: Creating a Conflict


1) Return to the main branch locally.
```bash
git switch main
```
![[Pasted image 20260108170025.png]]

2) Modify the same line in notes.txt that was previously changed in the feature branch.
```bash
nvim notes.txt
```
![[Pasted image 20260108170210.png]]

3) Save the change and upload it to GitHub
```bash
git add .
git commit -m "Editing the same line as dev branch"
git push -u origin main
```
![[Pasted image 20260108170315.png]]
5) Attempt to complete the Pull Request and observe the merge conflict
- 
![[Pasted image 20260108170408.png]]
5) Resolve the conflict so that the final file content is clear and correct.
![[Pasted image 20260108170448.png]]
```bash
Accept incoming change --> choosed this option
```

![[Pasted image 20260108170454.png]]

6) Save the conflict resolution.
![[Pasted image 20260108170531.png]]
7) Complete the merge successfully.
![[Pasted image 20260108170557.png]]




---

## Phase 7: Searching the Repository

1) Use Git to search the project files for a word that exists in notes.txt.

```bash
git grep <word> <fileName>
git grep "H" notes.txt
```
![[Pasted image 20260108170926.png]]

2) Perform another search using a different word.
`git grep "new" notes.txt `
![[Pasted image 20260108171030.png]]




---


## Phase 8: Inspecting Changes

1) Display **detailed information** about the most recent saved change, including file modifications. 
```bash
git log
git show <commit-id>
```
![[Pasted image 20260108171155.png]]

![[Pasted image 20260108171233.png]]

2) Display detailed information for an older saved change using its identifier.

```bash
git log
git show <commit-id> --> choose the older one
```
![[Pasted image 20260108171357.png]]
`git show <commit-id>`
![[Pasted image 20260108171426.png]]



---


## Phase 9: Undoing Commits

1) View the project history again.
```bash
git log
```
![[Pasted image 20260108171549.png]]
2) Undo the most recent saved change while keeping the file changes locally.
```bash
git reset --soft HEAD~1
git log
```
``

![[Pasted image 20260108171715.png]]
 Changes kept as they are in notes.txt
![[Pasted image 20260108171729.png]]

3) Undo another saved change and remove the file changes completely.
```bash
git reset --hard HEAD~1
```
![[Pasted image 20260108172527.png]]

I made another commit so it has parent and then used the command (because you can't make reset without having a parent commit, like just one commit).
![[Pasted image 20260108172535.png]]
Changes happened in notes.txt
![[Pasted image 20260108172600.png]]

4) Check the repository status after undoing the changes.
```bash
git status
```
![[Pasted image 20260108173319.png]]


5) Ensure the project history reflects all completed phases.
```bash
git log
```

![[Pasted image 20260108173427.png]]