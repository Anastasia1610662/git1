## 1. Создать учетную запись на ресурсе github.com

 git config --global user.name "Anastasia1610662"
 git config --global user.email "sentsova@mephi3.ru"
 
## 2. Создать локальный репозиторий в текущей папке. 

git init

## 3. Добавьте туда пустой текстовый документ. 

git add .txt

## 4. Сформируйте этот документ, создавая commit для каждого абзаца, не  менее 5 абзацев. 
git add Dok.txt

git commit -m "1 - абзац "
[master (root-commit) 929eea9] 1 - абзац
 1 file changed, 1 insertion(+)
 create mode 100644 Dok.txt

 git add Dok.txt

 git commit -m "2 - абзац "
[master e2edd2b] 2 - абзац
 1 file changed, 2 insertions(+), 1 deletion(-)

git add Dok.txt

git commit -m "3 - абзац "
On branch master
nothing to commit, working tree clean

git commit -m "3 - абзац "
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Dok.txt

no changes added to commit (use "git add" and/or "git commit -a")

 git add Dok.txt

 git commit -m "3 - абзац "
[master 6a7eda8] 3 - абзац
 1 file changed, 2 insertions(+), 1 deletion(-)

 git add Dok.txt

 git commit -m "4 - абзац "
[master d9c5349] 4 - абзац
 1 file changed, 2 insertions(+), 1 deletion(-)

git add Dok.txt

git commit -m "5 - абзац "
[master 5da3a32] 5 - абзац
 1 file changed, 2 insertions(+), 1 deletion(-)

## 5. Посмотреть статус текущего репозитория. 

git status

## 6. Добавить файл. 

git add Dok2.txt

## 7. Создать коммит, указать для него комментарий. 

 git commit -m "Новый документ"

##  8.Посмотреть протокол коммитов.

 git log

commit d5e26e670208e39ed77ac370364f160b4cbef83d (HEAD -> master)
Author: Anastasia1610662 <sentsova@mephi3.ru>
Date:   Thu Mar 14 04:32:05 2024 +0500

    Новый документ

commit 5da3a32815024b7ecacaccb120e44beb6476a858
Author: Anastasia1610662 <sentsova@mephi3.ru>
Date:   Thu Mar 14 04:24:32 2024 +0500

    5 - абзац

commit d9c5349c2a31b59275b34ae89b069732c17417c2
Author: Anastasia1610662 <sentsova@mephi3.ru>
Date:   Thu Mar 14 04:24:10 2024 +0500

    4 - абзац

commit 6a7eda8340f5faa8e0e975ed3cca8ef7b6954504
Author: Anastasia1610662 <sentsova@mephi3.ru>
Date:   Thu Mar 14 04:23:50 2024 +0500

    3 - абзац

commit e2edd2ba8e7f3a27175b285ed86d9df9b6dda3da
Author: Anastasia1610662 <sentsova@mephi3.ru>
Date:   Thu Mar 14 04:22:55 2024 +0500

    2 - абзац

commit 929eea984cf98be846f482ba881279f1c7a92d95
Author: Anastasia1610662 <sentsova@mephi3.ru>
Date:   Thu Mar 14 04:22:21 2024 +0500

    1 - абзац


 
## 9.Посмотреть изменения в файле по сравнению с последним коммитом.  

$ git log --oneline
d5e26e6 (HEAD -> master) Новый документ
5da3a32 5 - абзац
d9c5349 4 - абзац
6a7eda8 3 - абзац
e2edd2b 2 - абзац
929eea9 1 - абзац

git diff 5da3a32 d5e26e6

diff --git a/Dok2.txt b/Dok2.txt
new file mode 100644
index 0000000..4559259
--- /dev/null
+++ b/Dok2.txt
@@ -0,0 +1 @@
+Погода хорошая
\ No newline at end of file

## 10.Убрать изменения относительно последнего коммита из файла. 

git restore Dok2.txt

## 11.Просмотреть существующие ветки. 

git branch
master

## 12.Создать новую ветку. 

 git branch Branch2

## 13.Переключиться на другую ветку. 
 git checkout Branch2
Switched to branch 'Branch2'


## 14.Создать новую ветку и сразу же переключиться на нее. 

git checkout -b branch3
Switched to a new branch 'branch3'


## 15.Удалить ветку.  

git branch -d branch3
Deleted branch branch3 (was d5e26e6).


## 16.Добавить (merge) изменения из указанной ветки в текущую. 

git merge master
Already up to date.

## 17. Создать конфликт. добавила в файл текста

 git add Dok2.txt
git commit -m "Спор о погоде "
[Branch2 4d57be7] Спор о погоде
 1 file changed, 2 insertions(+), 1 deletion(-)

 git checkout master
Switched to branch 'master'

 git add Dok2.txt

git commit -m "Спор о погоде "
[master 54ed5b1] Спор о погоде
 1 file changed, 2 insertions(+), 1 deletion(-)

git merge branch2
Auto-merging Dok2.txt
CONFLICT (content): Merge conflict in Dok2.txt
Automatic merge failed; fix conflicts and then commit the result.

## 18 Посмотреть в каких файлах есть конфликты. 

$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   Dok2.txt

no changes added to commit (use "git add" and/or "git commit -a")

21.Устранить конфликты. 

git add Dok2.txt

git commit -m "Спор о погоде не решен "
[master 2cd9c96] Спор о погоде не решен


## 19.Переключиться на указанный коммит. 
git checkout 2cd9c96
Note: switching to '2cd9c96'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 2cd9c96 Спор о погоде не решен

## 20.Сделать ребазирование (rebase) текущей ветки. 

git rebase master

## 21.Удалить ветку.

git branch -d branch2

 git branch -d branch2
Deleted branch branch2 (was 4d57be7).

## 22.Пропустить текущий конфликтный коммит и перейти к следующему. 
git merge --abort
## 23.Отправить изменения из локального репозитория для указанной ветки в удаленный (дистанционный). 
git remote add origin https://github.com/Anastasia1610662/Practical_task.git
git push origin master

## 24.Создать копию репозитория.
git clone https://github.com/Anastasia1610662/Practical_task.git
