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
