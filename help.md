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

