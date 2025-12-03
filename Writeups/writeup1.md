Given a data.txt with the content below

12
7
91
8
27
30
Below is a common and useful logic one may use to submit a slurm array job

#SBATCH --job-name=warmup
#SBATCH --output=logs/%x_%A_%a.out
#SBATCH --error=logs/%x_%A_%a.err
#SBATCH --array=0-2
#SBATCH --cpus-per-task=1
#SBATCH --mem=2G
#SBATCH --time=00:10:00

i=0
# loop through each line in data.txt, `value` store line content
while read -r value; do
    if (( i % SLURM_ARRAY_TASK_COUNT == SLURM_ARRAY_TASK_ID )); then
        echo "$i: $value"
    fi
    # increment
    ((i++))
done < data.txt
Answer the following questions in your write-up:

How many slurm job will be submitted? --> 3 
What is the purpose of the if statement? --> distributes the lines of data.txt across the array tasks
What is the expected output in each *.out file? --> 0: 12, 3: 8
1: 7, 4: 27
2: 91, 5: 30