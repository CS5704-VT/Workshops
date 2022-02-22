# Package Managers

This notebook provides an overview of package managers and installing software to set up your development environment. You may continue to work with a partner to complete this activity, however each student will have to provide their own individual submission!

**An installation philosophy**
> *Avoid manual installation, automate with package managers!*

When possible, using a package manager can allow you to automate and streamline the installation of tools. Instead of hunting down the right website, finding the right version and dowload link, then clicking through an installation wizard---you let the package manager take care of all those manual steps for you! 

*Tip*: Later on, the ability to automate the installation of software environments becomes important in later stages of software development, such as continuous integration, or deployment.

We will learn how to use package managers to help use manage our system.

*Package managers* are tools for installing libraries and tools, which help manage dependencies and configuration of files and environment variables. 

There are generally two flavors of package managers. 

* *Binary* package managers typically install platform specific dependencies: (`brew`, `choco`, `apt-get`) 
* *Source* package managers typically install libraries you can use in your code: (`npm`, `pip`, `maven`)

Source package managers are useful for installing packages and libraries for specific programming langages. [`npm`](https://www.npmjs.com/) is the default package manager for Node.js and [`pip`](https://pip.pypa.io/en/stable/) for Python. Many package managers also have various options for specifying how to install packages. For example, to globally install a JavaScript package you can use `npm install -g <package-name>` (_You will need this information for later_).

If you do not have a package manager on your laptop, complete the following **_on your own_** personal machine. It will be needed for a future notebook in this workshop.

## Install a Package Manager on Your System


#### Installing on Linux

If you're using Linux, you typically already have a package manager, such as `yum` or `apt-get`. For example, on Ubuntu you can install packages using:

`apt-get install <package-name>`

> _You will need this information for later_.

#### Installing HomeBrew on Mac OS X

[Homebrew](https://brew.sh/) is a popular package manager for MacOS. Once HomeBrew is installed, you can use it to install other tools on your system using `brew install <package-name>`.

Let's check if we have `brew` installed on the system. If not, use the [Homebrew Install Instructions](https://github.com/CSC-DevOps/Course/blob/master/Content/Basics/setup/install-brew.md).
```bash|{type: 'command', platform:'darwin'}
brew --version
```

Here is an example of how to install the utility `wget`.
```bash|{type: 'command', platform:'darwin'}
brew install wget
```

#### Installing Chocolatey on Windows

[Chocolatey](https://community.chocolatey.org/) is a package manager for Windows. Once Chocolatey is installed, you can use it to install other tools on your system using `choco install <package-name>`.

We will check if we have choco installed. If not, use the [Chocolatey Install Instructions](https://github.com/CSC-DevOps/Course/blob/master/Content/Basics/setup/install-choco.md).

```bash|{type: 'command', platform:'win32', failed_when:"!stdout.includes('Chocolatey v')"}
choco --V
```


Important, when running commands that will make changes to your system, you may need to "Run (them) as Administrator". Notice, how when we run this command, `choco` warns us that we are not running inside an elevated shell.

```bash|{type: 'command',platform:'win32', stream: true}
choco install wget -y
```

We can try again, but this time, with a shell that has administrative priliveges:

```bash|{type: 'command', privileged: true, platform:'win32', stream: true}
choco install wget -y
```

Finally, we can remove `wget` using the `remove` parameter.

```bash|{type: 'command', privileged: true, platform:'win32'}
choco uninstall wget -y --remove-dependencies
```

#### Privileged Commands

Some commands, such as installation with package managers, may require adminstrative or super user privileges.

* **Mac/Linux:** To access a privileged shell, you simply can run `su` or prepend a command with `sudo` (i.e. **`sudo apt-get install <package-name>`**). `sudo` will cache your password, typically for 5 minutes, after successfully running a command. To avoid typing a password at all, you may add your user to the `/etc/sudoers` file. Note- it is recommended you make changes to this file using the special utility: `visudo`.

* **Windows:** If you need to run a command with admin, you must start a shell with admin privilege. There is typically an admin command shell available in the menu when right clicking the Windows Icon on the Task Bar. You can also get one from right clicking the Cmd executable in the search bar.

> _Tip:_ If opening up a cmd shell in admin mode, make sure you do not perform operations, such as `git clone` in your current directory (`C:\WINDOWS\system32`). Otherwise, you will be writing to a location that only admin will have access to which will make it difficult to run the commands/tasks you are intending on doing.

Let's practice installing useful software!

## 📒 Online Exercise: Install the packages

To submit this assignment, **take a screenshot** of the environment test results in Docable after clicking the CHECK button when this activity is completed. _Add this screenshot to the <u>main branch</u> of the PairProgramming repository from the previous activity!_

**Click on the following image to start the exercise:**

<a href="https://devops.docable.cloud/chrisparnin/v/61b3ed6a7db4f2fc6edefd59">
<img src="https://raw.githubusercontent.com/CSC-DevOps/Course/master/Content/Basics/resources/imgs/install-packages-notebook-preview.png">
</a>

> __*Tips:*__
> * If possible, open the activity below in a new tab to reference this page.
> * Docable uses a docker image based on Ubuntu 20. 
> * Pay attention to the command output: 
>   * If you get any error about permissions, try adding `sudo`
>   * If you see a message like `Do you want to continue? [Y/n] `, type 'y' and click Enter to continue (alternatively, use the `-y` command option)
>   * If it says you need to update, then update!

## [IDEs ⏭️](IDEs.md)

> This notebook is based on part of the [Engineering Basics](https://github.com/chrisparnin/EngineeringBasics/blob/master/setup/package-managers.md) workshop by [Dr. Chris Parnin](https://chrisparnin.me).