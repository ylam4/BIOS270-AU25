Setup terminal output:

ylam4@rice-02:~$ micromamba --version
2.3.3
ylam4@rice-02:~$ "${SHELL}" <(curl -L https://micro.mamba.pm/install.sh)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100  3059  100  3059    0     0   5463      0 --:--:-- --:--:-- --:--:--  5463
Micromamba binary folder? [~/.local/bin] 
Init shell (bash)? [Y/n] y
Configure conda-forge? [Y/n] Y
Prefix location? [~/micromamba] $SCRATCH/envs/micromamba
Running `shell init`, which:
 - modifies RC file: "/home/users/ylam4/.bashrc"
 - generates config for root prefix: "$SCRATCH/envs/micromamba"
 - sets mamba executable to: "/home/users/ylam4/.local/bin/micromamba"
The following has been added in your "/home/users/ylam4/.bashrc" file

# >>> mamba initialize >>>
# !! Contents within this block are managed by 'micromamba shell init' !!
export MAMBA_EXE='/home/users/ylam4/.local/bin/micromamba';
export MAMBA_ROOT_PREFIX='$SCRATCH/envs/micromamba';
__mamba_setup="$("$MAMBA_EXE" shell hook --shell bash --root-prefix "$MAMBA_ROOT_PREFIX" 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__mamba_setup"
else
    alias micromamba="$MAMBA_EXE"  # Fallback on help from micromamba activate
fi
unset __mamba_setup
# <<< mamba initialize <<<

Please restart your shell to activate micromamba or run the following:\n
  source ~/.bashrc (or ~/.zshrc, ~/.xonshrc, ~/.config/fish/config.fish, ...)
ylam4@rice-02:~$ source ~/.bashrc
ylam4@rice-02:~$ micromamba --version
2.3.3
ylam4@rice-02:~$ curl -s https://get.nextflow.io | bash

      N E X T F L O W
      version 25.10.0 build 10289
      created 22-10-2025 16:26 UTC 
      cite doi:10.1038/nbt.3820
      http://nextflow.io


Nextflow installation completed. Please note:
- the executable file `nextflow` has been created in the folder: /home/users/ylam4
- you may complete the installation by moving it to a directory in your $PATH


How many slurm job will be submitted? --> 3 
What is the purpose of the if statement? --> distributes the lines of data.txt across the array tasks
What is the expected output in each *.out file? --> 0: 12, 3: 8
1: 7, 4: 27
2: 91, 5: 30
