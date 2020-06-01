git remote show origin

git ls-tree -r master --name-only

git ls-files

[Adding an existing project to GitHub using the command line](https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line)

#### [Best practices for securely storing API keys](https://www.freecodecamp.org/news/how-to-securely-store-api-keys-4ff3ea19ebda/)
git-secret  
git-crypt  


#### git global and local profiles:  
You can configure an individual repo to use a specific user / email address which overrides the global configuration. From the root of the repo, run
git config user.name "Your Name Here"  
git config user.email your@email.com  

#### fatal: unable to access "git url" SSL certificate problem: certificate has expired  
git config --global user.name [username]  
git config --global user.email [email]  
git config –global http.sslVerify false  


