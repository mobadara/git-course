[![Last Updated](https://img.shields.io/github/last-commit/mobadara/git-course)](https://github.com/mobadara/git-course)

# **A Refresher Course on `git`**
Git is the most widely used distributed version control system today. It is known for its speed, flexibility and robust features.

<p style="color: #000000; background-color: #99aaff; border: 1 px solidrgb(116, 85, 255); padding: 5px;">
For this tutorial, it is assumed you have basic knowledge of the <code>terminal</code> or <strong>Window Power Shell</strong>
</p>

## **Installlation**
- On Debian/Ubuntu:
    ```bash
    sudo apt install git-all
    ```
- On Fedora/CentOS:
    ```bash
    sudo dnf install git
    ```
- Aech Linux
    ```bash
    sudo pacman -S git
    ```
- On Windows: [Click here](https://git-scm.com/download/win)
- On Linux: [Click here](https://git-scm.com/download/mac)

## **Verify your installation**
If the command is not found, install `git` using onw of the methods outlined above.
    ```bash
    git --version
    ```

## **Setting things up**
After installing `git`, you need to do a few things to customize your `git` environment. There are three types of environments as indicated in the `--<environment>` flag below: The system environment (`--system`), the global [user scope] (`--global`) environment and the local [project scope] (`--local`) environment. `--local` is infact the default. If you use the local scope, you need to run the setup command for every project.

The basic settings to get working with `git` are:

- **Identity**: Setting up your username and email address. The username is not neccessarily your GitHub username. 
    > The following commands are issued to the user scope.
      
    ```bash
    git config --global user.name "John Doe"
    git config --global user.email "someone@example.com"
    ```

- **Set your default branch**: By default, `git` names its default branch as `master` while GitHub uses `main`. It is advisable to set your default branch to `main`. Form `git` version `2.28` onwards, you can set your default branch.

    ```bash
    git config --global init.defaultBranch main
    ```

    > There are other commands such as setting up your default text editors. If you used the windows installer during installation, you would have notices that some of these settings were made during the installation setup.

- **Preview the Current Settings**: You can view your current settings using:
        
    ```bash
    git config --list
    ```
    - You can also check the value in a key by using the command below, for example, you want to see the current value stored in the `user.name` key.
    ```bash
    git config user.name
    ```

## **Getting help with `git` commands**
- For every command line tool, there is a `help` utility which explins how the tool is used. Anyone of the following commands can be used to quary the help utility of `git`.
    
    ```bash
    git help <verb>
    ```

    or

    ```bash
    git verb --help
    ```

    For example, to get the manpage help for the `git add` command, run:

    ```bash
    git  help add
    ```

    or

    ```bash
    git add -h
    ```

## **Initializing a Repository in a project Directory**
- To track your project with git, you need to make git know about your project. You can make your project a git repository by doing one of the following:
    - Initializing a git repository in your project directory
    - Cloning an existing repository
### **Initializing a `git` Repository**
- In this section, we will discuss initializing a git repository in your root project directory. 
- In your root project directory (`cd` into your project's root directory), use the command
    ```bash
    git init
    ```
    to initialize a git repository. This will create a hidden directory named  `.git` your project's root directory and this is the folder where everything that has to do with `git` is stored.

### **Clonig an existing repository**
- You can clone an existing repository using
    ```bash
    git clone https://github.com/<username>/<repo.git>
    ```
- This will copy everything about the project including snapshots of versions a folder named <repo> in your current directory where you run the `git clone` command. You can then `cd` into the directory and start working. **Be sure to edit the command to raname the username and the reponame. The angular brackets are not included. Example ```git clone https://github.com/mobadara/git-course.git```**

## **Managing files in your repository**
- Now that you have a repository (initialized or cloned), `cd` into the repository and start creating your project files and directory normally.
- Imagine you have two files in your project directory `index.js`, `index.html` with an hidden `.git` directory, you want to inform `git` about the two files. Use the command
    ```bash
    git add index.js
    git add index.html
    ```
- You have added the two files to the staging area of the repository. At this point, you need to commit your changes. This can be achieved by the command
    ```bash
    git commit -m "I just made a change to the index files"
    ```
- The `"I just made a change to the index` files" is call a commit message and can be any string as long as it describes why you committed.
- Finally, you push your changes to a remote repository. You need to inform your local repository (`git`) about your remote repository. You can register many remote repository with one local repository as long as they have different name reference. You will need to create a repository on your remote repository provider at this point and name it according to your project. Common remote repositories are [GitHub](https://github.com) and [Bitbucket](https://bitbucket.org). The name "origin" is commonly used to reference our first remote repository in our local repository. Register your first remote repository with the command:
    ```bash
    git remote add origin https://github.com/<remote-repo-username>/<remote-repo-name>.git
    ```
- With that done successfully, use the command below to send your project to the remote repository you registered above.
    ```bash
    git push -u origin main
    ```
    where `origin` and `main` above are the remote repository reference key and branch name respectively. Recall that you set your default branch name to `main`. Now, on a web browser, visit your remote repository landing page and find a copy of your project.

___
Muyiwa J. Obadara

