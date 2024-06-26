## Module 1 - Software Collaboration

Version Control - `A system that records all changes and modifications to files for tracking purposes.`
- Keep track of changes
- Provide access to history
- Revert and roll back

The benefits of version control
- Revision history
- Identity
- Collaboration
- Automation
- Efficiency

[Version Control Git terminology](02_github_git_cheatsheet.pdf)

Two types of version control systems
- Centralized version
  - contain a server (repository)  and clients 
- Distributed version
  - work in an offline state and only connect to a server to push and pull changes.

### Development Environments
Whenever businesses releases new features or change needs to verify that the code they do release is not going to cause any issues or bugs, they normally set up multiple environments for different ways to test and verify. A common practice is for teams to have a developer environment, a UAT or QA environment, and a staging environment. The main purpose of this flow is to find any potential issues that may arise due to changes or new features being added to the codebase.

#### Staging
  The staging environment should mimic your production environemnt to test the code in an environment that matches what production is in. This allows teams to spot or find any potential issues prior to them getting to production. The closer the staging environment is to your production, the more accurate your testing is going to be. Staging environments can also be used for testing and verifying new features and allow other teams including QA or stakeholders to see and use those features as a pre-trial. Staging should also cover all areas of the architecture of the application including the database and any other services that may be required. Areas that benefit from staging environments include:
  
__New features__ 

=> Developers submitting new features along with feature flags for turning them on and off should always do a testing round in a staging environment. They allow teams to verify that the feature works, it can be turned on and off via configuration flags and also that it does not break or interfere with existing functionality.

__Testing__

=> As the staging environment mimics your production environment, it's also a great place to run tests. QA teams will normally use it to verify new features, configuration changes or software updates/patching. The types of testing covered will be Unit testing, Integration testing and performance testing. All except performance testing can also be carried out in production. Performance can also be completed in production but only at specific times - usually out of hours as it will have a drastic effect on the user experience.

Sometimes it is not always feasible to have an exact replication either due to costs or time. Certain areas can be cut back - for example, if your service is load balanced on 10 virtual machines in production, you could still have 4 virtual machines in staging. The underlying architecture is the same but the overall performance may be different.

__Migrations__

Staging is a perfect place to test and verify data migrations. Snapshots can be taken from production and used to test your migration scripts to confirm your changes will not break anything. If in the case it does cause an issue, you simply rollback and try again. Doing something like a migration in production is extremely risky and error-prone.

__Configuration Changes__

Configuration can also cause headaches for teams, especially in a large cloud-based architecture. Having a staging environment will allow you to spot any potential issues or bottlenecks.

#### Production
Production is live. It's out there for people to see and/or interact with. Any issues or problems you may have had should have been caught and fixed in the staging environment. The staging area gives the team a safety net to catch these possible issues. Any code that is deployed to production should have been tested and verified before the deployment itself. 

__Downtime__

=> Downtime for any service especially customer facing will most likely be revenue impacting. If customers can not access or use your website or app to its full capabilities, it will most likely have a cost involved. Take for example an e-commerce company that allows users to buy goods and services online. If they release a new feature to their shopping cart which actually breaks the payment process, this will have an impact on customers not being able to buy goods online.

__Vulnerabilities__

=> Cyber-security should also play a big role in what gets released in production. Any updates to software such as patching or moving to the latest version should be checked and verified. This is also the same rule for not upgrading software when critical updates are released.

__Reputation__

=> Downtime or issues in production is damaging for a company as it does not instill confidence in end users. If something is down or broken it can cause the company to lose potential customers.

-------
## Module 2 - Command line

### 1. Command line

Command | Function
------- | --------
`mkdir lab`             | create directory lab
`cd lab`                | change to the lab directory
`touch file1.txt`       | create a file named file1.txt
`mv file1.txt dir1/`    | move file1.txt to directory dir1
`mkdir -p dir2/dir3`    | Use `-p` flag to create te parent directories if they do not exist. In this case, it will create the dir2 directory and then create the dir3 directory inside of dir2.
`mv file2.txt dir2/dir3` | move file 2 to dir3 directory
`mv file3.txt ../`       | move file3.txt to the lab directory
`ls -l`                  | list all files and ditectories in current working directory
`pwd`                    | check the current working directory

### 2. Pipe
A coding tool that allows the output of one command to be used as the input for a different command

`cat file1.txt`      => return the content in the file1.txt
`wc file1.txt -w`    => count the words in the file1.txt
`ls | wc -w`         => count the number of files
`cat file1.txt | wc -w` => return the word counts in file1.txt 
`cat file1.txt file2.txt | wc -w => return the total word counts of 2 files

### 3. Redirection

#### Standard Input (stdin)
- Purpose => used for taking input into a program
- Usage => programs read from stdin to receive data, which can be provided by the user or redirected from a file // another command

```cat > input.txt```
> This command is to add data into the file input.txt. After inputing data, `Ctrl + D` to end the command.

```cat < input.txt```
> This command is to display the content inputed.

#### Standard Output (stdout)
- Purpose => used for sending normal output from a program
- Usage: programs write their regular output to stdout. This output can be displayed on the screen, redirected t oa file // piped to another command.

```ls -l > output.txt```
> This command is to save the output of `ls - l` which generates a list of files of current directory with detailed information of each one (permissions, number of links, owner, group, size, and imestamp of the las modification).

#### Standard Error (stderr)
- Purpose => used for sending error messages and diagnostics from a program
- Usage => Programs write error message to stderr. This ensures that error messages are visible to the user, even if stdout is directed.

```ls -l /bin/usr > error.txt```
> This attempt to list the content of the `bin/usr` directory in long format and then, redirects the stdout to `error.txt`
> If `bin/usr` does not exist, `error.txt` will be created, but it will be empty since `stderr` is not directed and will still be shown in the terminal.

```ls - l /bin/usr 2> error.txt```
> This attempt to list the content of the `bin/usr` directory in long format and then redirects stderr to `error.txt`.
> If `bin/usr` does not exist, any error messages (ex. directory not found) will be written to `error.txt`.

```less error.txt```
> Open `error.txt` and view the contents of `error/txt` interactively.

```ls -l /bin/usr > error_output.txt```

```ls -l /bin/usr > error_output.txt 2>&1```
> This attempt to list the content of the `bin/usr` directory in long format and then redirect stdout to `error_output.txt`.
> `2>&1` is to redirect the stderr to the same file descriptor as stdout => ***Both stdout and stderr will be written to `error_output.txt`.

```less error_output.txt```

### 3. Grep (Global Regular Expression Print)
It is used for searching across files and folders as well as the contents of files.


