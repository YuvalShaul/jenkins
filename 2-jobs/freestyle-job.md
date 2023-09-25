# Freestyle Project(job)

In this walkthrough we'll create a new project(job).  
Not that Jenkins GUI looks better in Chrome, so you can go ahead and install Chrome in your linux machine.

## Create an example project

- Choose **New Item**, fill **exampbasic-freestyle** in the top edit fiels (project name)
- Select **Freestyle Project** and click on **OK** at the bottom
- Write something in the description window and save (use the **save** button at the bottom).  
(e.g:  **This job will run the python program and view the results**)
- Go back to configuration by clicking at the **configure** button on the left
- Note that the sections on the left are just locations inside the long configuration page.
- Note that checkboxes can open a configuration section


## Add steps

- Scroll down and find **Build Steps**, drope-down and select **Execute Shell**
- Paste the following command in the edit windows:
```
echo hello > /tmp/myfiles/hello
```
- Note that your command will not work, as there is no such a directory
- hot save at the bottom
- Click on **Build Now** at the left
- Your job appears at the bootom left, and seems to have failed.

## Fix you job

- Click on **Configure** at the left to go back to configuration mode
- Add another step (which will appear after the first one), and paste the following:
```
[ -d /tmp/myfiles ] || mkdir /tmp/myfiles
```
(we want to be able to run this multiple times and succeed)
- Now look for the menu sign (3 short line) left of the step name.  
Use it to drag the new step, and make it appear first, before the previous step.
- Save job and run again

## Build History

- Go to **Dashboard** level again and click **Build History**
- Explore the entries, and notice the output icon at the right side
