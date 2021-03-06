**********
Git guide
**********

#########################
Configuring your setup
#########################

Your config is stored in ~/.gitconfig. To list your config
::
    git config --list
    
A config file can be:

- system wide (stored in /etc/gitconfig)
  ::
    git config --system user.email jd@abc.com
    git config --system user.name "John Doe"
    
- global (stored in ~/gitconfig)
  ::
    git config --system user.email jd@abc.com
    git config --system user.name "John Doe"
    
- repo specific (.git/config) This is probably the best idea
  ::
    git config user.email jd@abc.com
    git config user.name "John Doe"
    
- a custom file 
  ::
      git config -file .gitconfig
      
  With contents
  ::
    [core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        
    [remote "origin"]
        url = git@bitbucket.org:username/xyz.git
        fetch = +refs/heads/*:refs/remotes/origin/*
        
    [branch "master"]
        remote = origin
        merge = refs/heads/master
        
    [user]
        name = John Doe
        email = jd@anc.com
        
#########
Branches
#########

- To create your own local branch 
  ::
    git branch my_branch_name
    
- To switch to created branch
  ::
    git checkout my_branch_name
    
- To push your local branch to remote
  ::
    git push orgin my_branch_name
    
- To rename a branch
  ::
    git branch -m <oldname> <newname>

#########
Merging
#########

There probably is a better way

- To ignore local changes and pull from remote. Please ponder if losing local changes is ok
  ::
    git reset --hard
    git pull origin master


###########################
Checking to remote issues
###########################

- Sometimes the agent is not running or the private key is not added if you have setup public key on remote
  ::
      eval "$(ssh-agent -s)"
      ssh-add ~/.ssh/yourkey.pem
      
      
      


