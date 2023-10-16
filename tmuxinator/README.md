# tmuxinator 

This folder contains tmuxinator session used to run all docker containers and ros nodes 
that enable near real-time human pose estimation and the robot arms control. 

In order to have all this `linux` scripts that are used, it is neccessary to source 
bash scripts provided in this folder with: 

```
source shell_scripts.sh
```

It is even better if you put sourcing command into `~/.bashrc` as follows: 

`echo "source <full_path_to_this_folder>/shell_scripts.sh" >> ~/.bashrc`

When you do so, you can use commands such as: 
`waitForDockerContainer, waitAndExec, waitForPing`... 

More about tmuxinator can be found [here](https://github.com/tmuxinator/tmuxinator) 
