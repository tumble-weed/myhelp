# rclone

__copyto__
rclone copyto src dst

Use the -P/--progress flag to view real-time transfer statistics

if src is file
    copy it to dst, overwriting an existing file if it exists
if src is directory
    copy it to dst, overwriting existing files if they exist
    see copy command for full details
This doesn't transfer files that are identical on src and dst, testing by size and modification time or MD5SUM. It doesn't delete files from the destination.

__copy__
(Does not transfer files that are identical on source and destination, testing by size and modification time or MD5SUM)
Note that it is always the contents of the directory that is synced, not the directory itself. So when source:path is a directory, it's the contents of source:path that are copied, not the directory name and contents.
rclone copy source:sourcepath dest:destpath

Let's say there are two files in sourcepath

sourcepath/one.txt
sourcepath/two.txt

This copies them to

destpath/one.txt
destpath/two.txt

Not to

destpath/sourcepath/one.txt
destpath/sourcepath/two.txt
__soft links__
-L , read up on this

__sync__
If you want to also delete files from destination, to make it match source, use the sync command instead.

# pgrep

2. Search for processes including their command-line options:
pgrep --full "process_name parameter"

# vast copy
The copy command uses rsync and is generally fast and efficient, subject to single link upload/download constraints.
vast copy ~/workspace 4330147:/workspace
That will copy the local ~/workspace (workspace folder of current user home directory) into the absolute path /workspace on instance 4330147.
# rsync

# ssh

# gather


out[i][j][k] = input[index[i][j][k]][j][k]  # if dim == 0
out[i][j][k] = input[i][index[i][j][k]][k]  # if dim == 1
out[i][j][k] = input[i][j][index[i][j][k]]  # if dim == 2

# torch meshgrid

# kill background task
The following command gives you a list of all background processes in your session, along with the pid. You can then use it to kill the process.

jobs -l

Example usage:

$ sleep 300 &
$ jobs -l
[1]+ 31139 Running                 sleep 300 &
$ kill 31139

# Get the upper triangular matrix

upper_triangular_matrix = np.triu(matrix)

# unzip

unzip into directory
unzip -d output_dir/ zipfiles.zip

# zip

zip multiple files and folders into single zip

zip my_final_filename.zip my_first_file my_second_file... my_last_file

#datetime now
datetime.datetime.now.strftime("%Y-%m-%d %H:%M:%S")
# kill background job
kill %1
kill %%

# trace
https://stackoverflow.com/questions/50558849/python-how-to-trace-function-execution-order-in-large-project

python -m trace --count -C . somefile.py ...

hunter

https://github.com/ionelmc/python-hunter

python -m trace --trace --ignore-dir /opt/conda/envs/gpnnenv  run_multithresh_saliency.py

# ls files with extensions
ls *.{mp3,exe,mp4}

# gp results and logging
voc_2007-extremal_perturbation_with_simple_scale_and_crop_with_gp_log_prob_sample1_freq_1_ncrops1_100-resnet50
voc_2007-extremal_perturbation_with_simple_scale_and_crop_with_gp_log_prob_sample1_freq_1_ncrops1_100-resnet50
voc_2007-extremal_perturbation_with_simple_scale_and_crop_with_gp_log_prob_sample1_freq_1_ncrops1_100-vgg16

/root/evaluate-saliency-4/elp_with_scales/scripts/log_many_saliency_dec13.py
ls -l voc_2007-extremal_perturbation_with_simple_scale_and_crop_with_gp_log_prob_sample1_freq_1_ncrops1_100-resnet50/*/*.xz | grep Oct | wc -l

# bash get path of script 
mypath=`realpath ${BASH_SOURCE[0]}`

# bash get input in function
function print_instance_name() {
    local instance_name="$1"
    echo "Instance Name: $instance_name"
}
# bash print all arguments
print_arguments() {
    echo "Number of arguments: $#"
    echo "All arguments: \$@ -> $@"
}
print_arguments arg1 arg2 "arg 3" arg4
# bash if modelname 50 or 16

# bash default arguments
arg1="${1:-avalue}"

# git reset
-- hard
This is the most direct, DANGEROUS, and frequently used option. When passed --hard The Commit History ref pointers are updated to the specified commit. Then, the Staging Index and Working Directory are reset to match that of the specified commit. Any previously pending changes to the Staging Index and the Working Directory gets reset to match the state of the Commit Tree. 

This means any pending work that was hanging out in the Staging Index and Working Directory will be lost.
Here we have executed a "hard reset" using the --hard option. 
Git displays output indicating that HEAD is pointing to the latest commit dc67808. Next, we check the state of the repo with git status. Git indicates there are no pending changes. We also examine the state of the Staging Index and see that it has been reset to a point before new_file was added. Our modifications to reset_lifecycle_file and the addition of new_file have been destroyed. This data loss cannot be undone, this is critical to take note of.
--mixed
This is the default operating mode. The ref pointers are updated. The Staging Index is reset to the state of the specified commit. Any changes that have been undone from the Staging Index are moved to the Working Directory. -mixed is the default mode and the same effect as executing git reset. Examining the output from git status and git ls-files, shows that the Staging Index has been reset to a state where reset_lifecycle_file is the only file in the index. The object SHA for reset_lifecycle_file has been reset to the previous version.
The important things to take note of here is that git status shows us that there are modifications to reset_lifecycle_file and there is an untracked file: new_file. This is the explicit --mixed behavior. The Staging Index has been reset and the pending changes have been moved into the Working Directory. Compare this to the --hard reset case where the Staging Index was reset and the Working Directory was reset as well, losing these updates.

--soft
When the --soft argument is passed, the ref pointers are updated and the reset stops there. The Staging Index and the Working Directory are left untouched.  Examining the repo state with git status and git ls-files shows that nothing has changed. This is expected behavior. A soft reset will only reset the Commit History. By default, git reset is invoked with HEAD as the target commit. Since our Commit History was already sitting on HEAD and we implicitly reset to HEAD nothing really happened.o better understand and utilize --soft we need a target commit that is not HEAD.The log output now shows that there is a single commit in the Commit History. This helps to clearly illustrate what --soft has done. As with all git reset invocations, the first action reset takes is to reset the commit tree. Our previous examples with --hard and --mixed have both been against the HEAD and have not moved the Commit Tree back in time. During a soft reset, this is all that happens.--soft does not touch the Staging Index, so the updates to our Staging Index followed us back in time through the commit history

# github rawfile
You can directly use GitHub's raw content URL to serve files. Replace blob with raw in the file URL to get the raw content link. For example: https://github.com/username/repository/raw/main/path/to/file.ext

# concatenate to string
A="X Y"
A+=" Z"
echo "$A"

# arrays in bash

declare -a array
array=(one two three)

echo "${array_name[@]}"

# grep exclude
grep -v

# output of ls into an array
files=$(ls)

# Initialize an empty array
file_array=()

# Use a while loop to read each line of the ls output into the array
while IFS= read -r file; do
    file_array+=("$file")
done <<< "$files"
# find sh files in the current directory
find . -maxdepth 1 -type f -name '*.sh'
# vim lookbehind
In vim, lookbehind uses the special @ symbol, rather than the perl (?<=somestring) syntax.
foo \zsbar\ze baz matches the “bar” in foo bar baz. But the whole pattern is still required
\(atom\)\@<= 
atom is he look behind string

# bash check if string is empty
myVar=""
if [ -z "$myVar" ]; then
    echo "myVar is empty"
else
    echo "myVar is not empty"
fi

#using completion
compgen -W "eric tom" -- "c"

_mycommand() {
    local cur prev
    COMPREPLY=()
    cur="${COMP_WORDS[COMP_CWORD]}"
    prev="${COMP_WORDS[COMP_CWORD-1]}"

    # Get a list of files in the config_files/ folder
    files=$(find config_files/ -type f -printf "%f\n")

    # Use compgen to generate autocompletion suggestions
    COMPREPLY=( $(compgen -W "$files" -- "$cur") )
    return 0
}

complete -F _mycommand mycommand

# git pull but dont overwrite
git stash --include-untracked
git pull
git stash pop

# multiple commands in watch per line
watch -n 1 '{
    echo "Command 1 output"
    ls -l
    echo "Command 2 output"
    df -h
    # Add more commands as needed
}'

# how do i copy the output of a bash command to the clipboard, so that i can paste it using ctrl+v
sudo apt-get install xclip
your_command | xclip -selection clipboard
If you prefer to use xsel, the syntax is quite similar:
your_command | xsel --clipboard
Error: Can't open display: (null)

#vim turn off regex mode
\V (capital v)

# ssh and change to directory
ssh -t vast-118 'cd /root/evaluate-saliency-4/elp_with_scales && exec bash -i'
This command uses the `-t` option to force a pseudo-tty allocation,

# bash interating over arrays whose elements have spaces
WRONG:
ar=("1 2" "3 4")
for el in ${ar[@]};do
    echo $el
done
"""
1
2
3
4
"""
CORRECT
ar=("1 2" "3 4")
for el in "${ar[@]}";do
    echo $el
done
"""
1 2
3 4
"""
# bash loop variable
count=1
((++count))
in Bash, the use of double parentheses (( ... )) is a syntax for arithmetic evaluation. The double parentheses are used for arithmetic operations, including incrementing or decrementing variables.

# bash check value less than
 [ "$count" -le 5 ];
# <,<<,<<< in bash
     < is used for input redirection from a file.
    << is used for creating a here document, allowing you to provide a block of text as input to a command.
    <<< is used for creating a here string, allowing you to provide a string as input to a command.
# vim syntax highlighting
    https://vi.stackexchange.com/questions/40208/syntax-highlighting-for-shell-scripts-broken
# matplotlib pyplot reverse order of axis in scatter plot
# Reverse/flip the order of the axes
ax.invert_xaxis()
ax.invert_yaxis()
ax.invert_zaxis()

# vim paste
For pasting in vim while auto-indent is enabled, you must change to paste mode by typing:

:set paste

Then you can change to insert mode and paste your code. After pasting is done, type:

:set nopaste

to turn off paste mode. Since this is a common and frequent action, vim offers toggling paste mode:

set pastetoggle=<F2>

# TRY  git between directories
git diff --no-index path/to/repo1/file.txt path/to/repo2/file.txt

# access particular row of array
my_array=("apple" "banana" "cherry" "date")
echo "First element: ${my_array[0]}"

# trap error handling
function dummy(){

trap cleanup EXIT
}

# bash dictionary 
declare -A my_dict
my_dict["apple"]="fruit"
echo "Type of coffee now: ${my_dict["coffee"]}"

# difference between [[ and [ in bash test
    [ ]: The single square brackets are the traditional test command. They require spaces around the operands and operators.
    [[ ]]: The double square brackets are an enhanced version introduced in Bash that allows for more features and flexibility. They don't require spaces around the operands and operators, and they support additional features like pattern matching and regular expressions.
    [ ]: Variables and strings inside single square brackets should be quoted to avoid issues with spaces or special characters.
    [[ ]]: Quoting is often not necessary inside double square brackets, though it doesn't hurt to use quotes for consistency.

# bash collect all command line arguments into a function and if no argument is given take default arguments
# embed tmux within tmux
TMUX= tma t-inner
# different types of checks ( existence of file, of dir, variable, )
# how  much time did a bash command take
# read in a file in bash
# sed awk in bash
# bash identify unset variables
 bash -u ./add_values.sh
./add_values.sh: line 4: tow_val: unbound variable
# Trap for Debug
We can utilize the DEBUG trap feature of Bash to execute a command repetitively.  The command specified in the arguments of trap command is executed before each subsequent statement in the script.

Let’s illustrate this with an example:

trap 'echo "Line- ${LINENO}: five_val=${five_val}, two_val=${two_val}, total=${total}" ' DEBUG
five_val=5
two_val=2
total=$((five_val+two_val))
echo "Total is: $total"
total=0 && echo "Resetting Total"

# vim open files side by side:
vim -O file1 -O file2
# vim insert line below the line with a search result
:/example/s/$/\rNew line text

