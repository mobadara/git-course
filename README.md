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

___
Muyiwa J. Obadara

