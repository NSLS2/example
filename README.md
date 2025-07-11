## How to Build this Classical IOC `example`
1. Type these commands in somewehre, i.e your home directory `~/example` on a terminal. Type `linux-x86_64` for the prompt `What architecture do you want to use?`. 
    ```
        mkdir example
        cd example
        makeBaseApp -t example example
        makeBaseApp -i -t example example
        make
    ```
    
2. On NSLS2 internal GitHub, https://github.com/NSLS2, create a repository for the above IOC `example`. `Owner` is `NSLS2`, `Repository name` is `example`. You MUST choose `Public` instead of `Internal`. You may choose `BSD 3-Clause "New" or "Revised License"`.

3. Back to your terminal, put the IOC `example` to the GitHub repository.
    ```
        git init
        git branch -M main
        git remote add origin https://github.com/NSLS2/example.git
        (or git remote add origin git@github.com:NSLS2/example.git)
        git pull origin main
        git status
        git log
    ```
    Now, create a file `.gitignore` which contains something like this:
    ```
        /bin
        /configure/CONFIG_SITE.local
        /configure/O.*
        /configure/RELEASE.local
        /db
        /dbd
        /include
        /lib
        /*App/Db/O.*
        /*App/src/O.*
    ```
    Finally, track files, make a commit, push it out:
    ```
        git add .
        git commit -m "first working example IOC"
        git push
    ```
