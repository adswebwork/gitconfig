#GIT Config
#will add comments soon
[user]
                name = user
                email = user@domain.com
[color "branch"]
                current = red
                local = yellow
                remote = green
[color "diff"]
                meta = yellow
                frag = magenta bold
                old = red bold
                new = green bold
                whitespace = white reverse
[color "status"]
                added = green
                changed = yellow
                untracked = red
[core]
                whitespace=fix,-indent-with-non-tab,trailing-space,cr-at-eol
                autocrlf = true
                editor = vim
[push]
                default=tracking
[alias]
#File manipulation          
 
                #commit
                c = commit
                cm = commit -m
                cam = commit -am
 
                #difference
                d = diff
 

#check unpushed commits
                #uncommited files
                u = cherry -v

                #cherry picking
                cp = cherry-pick
 
 
                #pulling
                l = pull --rebase
                rc = rebase --continue
                rs = rebase --skip
                p = push
                pom = push origin master    		#push current branch master
                pod = push origin development		#push current branch development
		psu = push --set-upstream origin	#shortcut for common warning

#sets the upstream of origin to remote branch name
                po = push origin

                #testing remote connections
                r = remote -v

#check out branch
                co = checkout
                sw = checkout #switch
                sb = checkout #switch branch

#switch branch
                f = git fetch #synch up latest items in repo with local versions
 
                #git branches
                b = branch
                br = branch -ravv 		#check remote and local branch status
                bv = branch -v
                bm = branch --merged
                bnm = branch --no-merged
                db = branch -D
                rrb = push origin :
                drb = push origin --delete
                cb = branch
 
                #repo cleanup
                pr = remote prune origin
                pl = fetch -p
 
                #merging
                mg = merge origin/master
                tool = mergetool
                flush = reset --hard origin/master
 
                #git hash
                gh = rev-parse --verify HEAD
 
                wipe = stash save --keep-index
#Status
        s = status
                i = init
#Git ignore
                h = "!git ls-files -v | grep '^h'| cut -c 3-" #used to list all hidden files 
                hide = update-index --assume-unchanged
                unhide = update-index --no-assume-unchanged ^M
#Locate text
                f = "!git ls-files | grep -i"               
                grep = grep -Ii
                gr = grep -Ii
                fnd = log --pretty=\"format:%n%n%C(cyan) %cn - %H - %C(yellow) %ar %n %n %C(yellow)%s %d\\ %C(green) %n %C(cyan)\" --name-status --grep
#Git logs
                filelog = log -u
                fl = log -u
 
                ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cgreen\\ [%cn]" --decorate --numstat
                ls = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cgreen\\ [%cn]" --decorate
 
                ld = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cgreen\\ [%cn]" --decorate --date=relative
                la = log --pretty=format:"%C(yellow)%h%Cred%d\\ %C(green)[%cn]\\ %C(cyan)%ar\\ %Creset%s" --decorate
 
                le = log --oneline --decorate
                dl = "!git ll -1"
                dlc = diff --cached HEAD^
                wc = whatchanged
 
#List aliases
                q= "config --get-regexp alias"
                a= "add ."
                aa= "add --all"
#Stashes
                stashes = stash list
                sl = stash list
                sa = stash apply
#applies the last stash
                sas = stash apply stash@{$1}
                sad = stash apply drop@{$1}
 
[branch "master"]
                remote = origin
                merge = refs/heads/master
[gui]
