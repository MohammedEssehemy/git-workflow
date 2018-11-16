### Git workflow

* 4 persistent branches:

     1- master  
     2- testing  
     3- staging  
     4- development

_____

## Get the repository

* clone the repository on your machine:

        git clone url #url is the repository url

## Feature/Issue workflow

* each new feature/issue created with new branch forked from development:

        git checkout development
        git pull
        git checkout -b feature/my-awesome-feature
edit, commit, push your commits as needed:

        git add .  #You can select the needed files
        git commit -m 'commit message'
        git push --set-upstream origin feature/my-awesome-feature # first time only after that use git push
when you finish your work, pull the development branch and solve any conflicts:

        git pull origin development
then open a pull request to development branch

* You can use [gitlab-jira integration](https://docs.gitlab.com/ee/user/project/integrations/jira.html#closing-jira-issues) to close issues directly from gitlab

* code will be peer-reviewed, when all issues are solved it will be merged on to development     

* after branch was merged, you can delete the local branch if you like:    

        git checkout development  
        git branch -d feature/my-awesome-feature

_____

## Hotfix workflow

* hotfixes are forked from `staging` or `master` as it requires:  

        git checkout master  # or staging (as needed)
        git pull  
        git checkout -b hotfix/fix-bug   

when you finish your work, pull the base branch and solve any conflicts:

then open a pull request to base branch

* You can use [gitlab-jira integration](https://docs.gitlab.com/ee/user/project/integrations/jira.html#closing-jira-issues) to close issues directly from gitlab

* code will be peer-reviewed, when all issues are solved it will be merged on to base branch and all lower branches
* after branch was merged, you can delete the local branch if you like:    

        git checkout development  
        git branch -d hotfix/fix-bug  
