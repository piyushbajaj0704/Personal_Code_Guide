### GNU Midnight Commander – mc: 
>> brew install mc
>> mc
https://jonathansblog.co.uk/mc-for-mac-osx
 
 
### Cool Cmds:
> sudo !!
> tig status
> tig log
> cat system.log | grep error
> history
> history | grep XYZ
Some long running cmd; say “Done”

### Mac:
Move screens: `Ctrl + Left/Right Arrows`

### Terminal:
Move to start of line: `Ctrl + a`
Move to start of line: `Ctrl + e`
Move one char back: `Ctrl + b`
Move one char forward: `Ctrl + f`
Move one word back/forward: `Option + Left/Right Arrows`


### Git Basics:
> git push
> git pull
> git checkout -b [name_of_your_new_branch]
> git push -u origin [branch_name]
> git push origin --delete [branch_name]  (To Delete a remote branch)
> git log
> git reset (revert changes made to the index)[reset all of your unpushed commits to master]
> git reset <file> or else git reset (undo git add before commit)
> git reset --hard (Discard the local changes, cautious you can always stash)
> git reset --hard origin/master (resets my (local) copy of master (which I assume is screwed up) to the correct point, as (remote) origin/master)
> git checkout . (Revert all local uncommitted changes (should be executed in repo root) OR [git stash, git stash drop]
> git checkout [some_dir|file.txt] (revert uncommitted changes only to particular file or directory)
> git clean -fdx (Remove all local untracked files, so only git tracked files remain) [use -n for preview of files to be deleted]
> git revert <commit 1> <commit 2> (Revert a change that you have committed)
> git stash, git checkout diff_branch, git stash apply, git stash drop (Switch branch without discarding local changes)

Sync a branch with master:
> git checkout master
> git pull
> git checkout branch
> git merge master
   
### Kubernetes:
> minikube start
> kubectl get nodes
> docker --version           
> docker-compose --version       
> docker-machine --version     
> minikube version     
> kubectl version --client

### Postgres General Commands:
> which psql
> ps aux | grep postgres
> ps -f -u postgres : should list postgres processes
> sudo -u postgres /usr/pgsql-9.5/bin/postgres -D /var/lib/pgsql/9.5/data
> systemctl status postgresql-9.5.service
> systemctl status (This made all the processes run)
> sudo lsof -n -u postgres | grep LISTEN or sudo netstat -ltnp | grep postgres (list the PostgreSQL processes in your environment)
Configuring postgresql.conf : /var/lib/pgsql/9.5/data/postgresql.conf

If is configured to listen and handle request in port 5432: cat /etc/services | grep 5432
Check whether the service is active or not : service postgresql status
Checking whether a specific port assigned for service relates to PostgreSQL Database Server is actively listening or not by executing the following command : netstat -tulpn | grep 5432
Run Postgres DB terminal: sudo -u postgres psql
 
This lists databases:
SELECT datname FROM pg_database
WHERE datistemplate = false;
 
This lists tables in the current database:
SELECT table_schema,table_name
FROM information_schema.tables
ORDER BY table_schema,table_name;
 
\c “database”
