# Running Linux on Windows

Linux is an open-source operating system.
Some of you may know it as the "hacker" OS or as a very nerdy piece of software, but it is actually used to power the majority of the world's websites and servers.
Some interact with Linux over a graphical interface like you may be used to, but most use a command line interface, like the terminal you'll be using in this tutorial, to use Linux.
In fact, many of our CTF problems run on Linux, and our binary exploitation problems are Linux programs!

Windows is a pretty cool operating system, but it can't run Linux (or mac) programs natively.
However, there is a tool that can allow you to run these programs.
The aptly named tool ~~Linux Subsystem for Windows~~ Windows Subsystem for Linux lets you run a Linux environment on your Windows computer.

## Setup

1. Launch Powershell as an Administrator. You can find this by using Windows Search.

    ![](images/win-search-ps.png)

1. In powershell, copy and paste the following command:
    ```
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```

    You should see that the WSL feature is now enabled.

    ![](images/win-ps-install.png)

1. Reboot your computer.

1. Install WSL from the [windows store](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6).
    When it finishes installing, you should see a "Launch" button.
    Yeah, go ahead and click on that.

    ![](images/win-store-ubuntu.png)

1. When you first launch WSL, you will need to create a user account.
    You can enter whatever username/password you want here.

    ![You might notice that this has a blue border instead of an orange one. I already had WSL installed, so this image is from Microsoft's documentation. Keen eye!](images/win-wsl-config.png)

1. Congratulations!
    You now have a Linux environment on your Windows computer!

    ![](images/win-installed.png)

## Next Steps

From here, you can follow any Linux tutorial to move around and interact with the Linux environment.
If you don't know where to start, we recommend [Ryan's Tutorials](https://ryanstutorials.net/linuxtutorial).


## Accessing Your Existing Files

Now, if you've been following along, you might be wondering, "Gee, where are all my files?"
Your `C:\` drive will be mounted at `/mnt/c`.
You can then access any file on Windows.
For example, if I wanted to view my desktop folder at `C:\Users\ed\Desktop`, I could use `cd /mnt/c/Users/ed/Desktop`.

Does that seem like a lot of work?
You can create an alias for that command.
Type `alias name="cd path"`, where `name` is the name of your alias and `path` is the path your want to alias to.
Then when you type `name` into the terminal, it will run the `cd path` command.
To persist this change, add it to your bash config with `nano ~/.bashrc`.
Use the arrow keys to scroll to the bottom of the file, and add that alias command.
Save and close by hitting `Ctrl-X` and `Y`.
Now, when you open a new WSL terminal, you'll have the alias for quick movement!

## Help! I'm Stuck!

Feel free to contact the CS Camp CTF staff, and we'll help you figure out any problems you might have.

Enjoy CS Camp, and have a nice summer!