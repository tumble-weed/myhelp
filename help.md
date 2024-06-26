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
# embed tmux within tmux
TMUX= tma t-inner
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

# bash why ${var1_var2} , does _ act as a concatenation?
no. tried it out
# python using the different arg name than variable name in argparse
parser.add_argument('--save-dir', dest='save_dir',
                    help='The directory used to save the trained models',
                    default='save_temp', type=str)
# rclone check if files are the same
rclone check
# latex new command
\newcommand{\todo}[1]{\textcolor{#1}}
# bash capture output of ls in an array
When you use the backticks (``) or the $(...) syntax to capture the output of a command, the result is treated as a single string, not as an array.
readarray -t my_array <<< "$(ls)"
#=====================================================
# python click in python
# js sound input in browser for python app
# bash or conditions in if ( if a=='y') or (if a == 'Y')
[ $var1 == "a" ]  && [ $var2 == "b" ]
[ $var1 != "a" ]  && [ $var2 == "b" ]
# bash different types of checks ( existence of file, of dir, variable, )
file [[  -f "file" ]]
directory [[ -d "directory" ]]
variable [[ -v varname ]]
# bash cat + search
use less -e
# vim getfilename from a env variable and open it
# js interpeter/ compiler
node
# python save the audio file and then download it
# js fetch
# js what is a blob
# js what is POST and GET?
# js => function

# python uvicorn start app
uvicorn server:app --reload --host 0.0.0.0 --port 8002
# git different gitusers for different directories
# or set crenetials when you login, and use that just within that session. in envvariables $GH
# passing variables to subshells


No, you can't interact with the parent shell from a subprocess it spawned (without that shell's active participation, which isn't reasonably/practically available in the scenario at hand) -- but you can export your variables to make them accessible to new shells started in child processes.

Running

set -a

...will make any variable defined going forward be automatically exported to the environment, even without an explicit export command.
# Environment vars vs shell vars

Explanation

Environment variables and shell variables are two entirely different concepts, but as we manipulate them in a similar way in bash, it's easy to get confused.

    Whenever a process is created (by fork), it may include an environment, given by its parent at fork-time. The child process may then access and modify its content. How this is done as a user depends on the program :
        In vim, you can access an environment variable like this : :echo $foo
        In bash, you can access it like this : $ echo "$foo"
        In most programming languages, you can access it with a syntax coherent with the rest of the language, such as ENV['foo'] in ruby

    On the other hand, a program may allocate memory for any internal use, but notably, it will quite often define and use variables. Once again, this depends on the program :
        In vim, you would use the :let command to assign an internal variable
        In bash, you would assign a variable with $ foo='bar', and then read it with $ echo "$foo"
        In most programming languages, you have a variation of the foo='bar' syntax, sometimes with type declarations, etc

As you can see, bash uses the same syntax to read an environment variable and one of its own private variables, which can lead to some confusion.

When you execute vim from your bash shell, the environment is copied over from the parent process (bash) to the child (vim), but the private memory of bash (including the variables you may have defined) are not.

Thus, accessing them from the child process would require some inter-process communication mechanism, between parent and child. While technically doable, this option is not implemented in bash nor vim.
Solution

In order for your variable to be accessible from vim (or any forked process, for that matter), you need it to be present in the environment of your vim process.

Several options to do that :

    $ export foo='bar' : This will mark your variable for export to the environment of subsequently executed commands. That's what you want in most cases.
    $ foo='bar' vim : This adds your variable to the environment of this vim command. Very useful for troubleshooting, or for one-liners.
    $ set -a : As you can see in bash manpage, this marks every subsequent definitions for export to the environment of subsequent commands. It's essentially equivalent to prepending every subsequent definition by export.

To go further

    The question uses the :!echo $foo syntax to display the value of foo, which is yet another usecase. The ! here is actually an escape sequence that allows you to execute a shell command from vim.

    However, vim cannot execute anything in the parent shell (the one you executed the vim command in), so it creates a new bash shell in a child process, executes echo in it, and displays the result.

    In the current case, the result is mostly the same, but it could easily be misleading in other situations, so it's important to understand what is happening here.

    There is another vim syntax, using expand, that allows one to lookup variables : :echo expand("$foo")

    It however works entirely differently.

    If no internal variable named foo exists, vim will invoke a shell to look it up (similarly to what ! would do).

    This options is way slower than an environment lookup, and not recommended for most usecases.

# using " around array might have a different usage from when used around a single element
# alias in ipdb
# js what are audio blobs in the browser?
# js create a python script to send a request to a webpage
# make bash aliases available in vim
set shellcmdflag=-ic
# bash integer expression expected error
if [ "$DBG_TORCHRAY" -eq 1 ];then
    pythond generate_run_script.py --json_filename run-jsons/$json_filename
else
    python generate_run_script.py --json_filename run-jsons/$json_filename
fi
# bash extract directory from type vimtorchraysmallerdataset is aliased to `vim /root/evaluate-saliency-4/elp_with_scales/torchray/benchmark/smaller_datasets.py'
# python get argmax of list
max_epoch = max(enumerate(epochs),key=lambda k:k[1])[0]
# vim persist copies between session
# tmux check if tmux session exists
# tmux send command to tmux session
# bash view colored output with less
https://unix.stackexchange.com/a/19319
alias rless='less -r'
# passing named arguments to bash files
ENV=1 cmd
function f1()
{
    echo "$env1"
}

function f2()
{

    env1=1 f1
    echo "hi"
}

f2
# git change last commit message
# bash run in directory context manager
function runindir1(){
    d="$1"
    shift
    inner="$*"
    curdir=`pwd`
    cd $d
    ${inner}
    trap "cd $curdir" EXIT
    trap "cd $curdir" ERR
    }
f1(){
runindir1 /root/vast-utils
cat setup.sh
}
f1
# bash run a command with spaces 
eval $cmd
# bash exporting variables to subshells
No, you can't interact with the parent shell from a subprocess it spawned (without that shell's active participation, which isn't reasonably/practically available in the scenario at hand) -- but you can export your variables to make them accessible to new shells started in child processes.

Running

set -a

...will make any variable defined going forward be automatically exported to the environment, even without an explicit export command.
# bash order of runs when multiple traps are set
Only the last one runs
f(){
    trap "echo 'i was first'" EXIT
    trap "echo 'i am second'" EXIT

}
f
i am second
# bash cascading of command line options in bash
!!YES
f0(){
    env1=1 f1
    echo "f0 $env1"
    }
f1(){
    echo "$env1"
    f2
    }
f2(){
    echo "$env1"
    }
f0
# ssh forward multiple ports in same
The -L option can be specified multiple times within the same command. Every time with different ports. I.e. ssh -L localPort0:ip:remotePort0 -L localPort1:ip:remotePort1 ...
# subclass torch tensor to catch nans:
https://discuss.pytorch.org/t/subclassing-torch-tensor/23754/5
# python fastapi mounting static files
    app.mount("/", StaticFiles(directory=".", html=True), name="static")
# as a dictionary as_dict(a,b,c) = {'a':a,'b':b,'c':c}
# bash arrays:
$ar
ar[@]
$ar[@]
${ar[@]}
"${ar[@]}"
# bash see last command in history
history | tail -n 1
# bash history remove element at 2072
<SPACE>history -d 2072
# else if in bash is elif
elif then
#first n characters of a string
If the variable is: FOO="qwertzuiopasdfghjklyxcvbnm"
then
 echo ${FOO:0:10}
# bash start from n till end
 ${FOO:3}
# vim reopen fileat same location
" Uncomment the following to have Vim jump to the last position when
" reopening a file
if has("autocmd")
  au BufReadPost * if line("'\"") > 0 && line("'\"") <= line("$")
    \| exe "normal! g'\"" | endif
endif
# linux checking against user password
if pamtester pam_unix.so $USER authenticate; then
    echo "Authentication successful. You may proceed."
    # Your command or script logic goes here
else
    echo "Authentication failed. Access denied."
fi
# bash providing encrypted password to bash script
https://www.makeuseof.com/encrypt-password-shell-scripts-linux/
# sed adding a line before the first line
sed -i '1s/^/hello this is before the first line\n/' myfile.txt
# do local variables commute to inner function calls?
f1(){
    echo $v
    local v2=2
    }
f0(){
    local v=1
    f1
    echo ${v2}
    }
f0
1
0
# python debugging edit current file
(ipdb) interact
file = __file__
%edit $file
# vim bookmark a line
If you type ma , it will create bookmark on the current line at the current location with name a.
For example, if you type `a , it will take you to the bookmark with name “a”. i.e It will take you to the place where the cursor is high-lighted in the above Fig 1.
# nano syntax highlighting
/usr/share/nano
~/.nanorc
# nano auto indent
set autoindent
# nano tab expansion
set tabsize 4
set tabstospaces
# bash empty array
local a=()
# bash add elements to an array
ar+=("a")
# bash watch cant run aliases


It's nothing to do with users.

Aliases are only expanded in the interactive shell for which they are defined - so an interactive bash shell if you defined them via ~/.bashrc, or an interactive zsh shell if you define them in ~/.zshrc for example.

The watch command invokes commands via a non-interactive /bin/sh shell.

By aliasing watch itself, as alias watchh='watch ' (with a trailing space) and then using watchh gpu, you force the current interactive shell to expand gpu before it's passed to watch.

Note that in zsh, aliases may be defined as global which allows them to be expanded anywhere in a command - avoiding the need to alias watch with a trailing space.
# why do we start fastapi with uvicorn
    . what is uvicorn
    . what will happen if we dont have uvicorn
# what is asgi and wsgi
# bash cd only autocomplete directories 
# bash vim type auto complete, cycle through full filenames
# python what does traceback do
# html how do i save an audio blob from a wav file
# python how do i test a fastapi code without using the html page
# bash select only those rows from ls that are after Jan 2
# vim noremap, <leader>
# vim write a function to copy the text visually selected, to be copiedto a file. 
# vim write a function then when you place your cursor in a new file and do :pastf it will paste from that file
# vim free hotkeys for this
# vim go to end of indentd block
# vim basic vim function
# bash how to make a new user in linux
# bash make files
# bash read text file line by line and arrange it in reverse order
# python how can we have better communication about what is returned from a function ( e.g. if it is a list or dictionary). Pydantic for debugging?
# python similarly how can be have better communication about the inputs to a function
# use pytest to run attribution benchmark to ensure it goes on without failure?
# python modify the next line to be xecuted -> use this to early exit, or break. ( modify the call stack)
# python regex module basic usage
# python instead of installing import a folder so that you can refer to its elements by using . notation
# python your own language to parse todo
# bash stop loop if a command fails
# bash ls sort by date
# bash subshell and shell
# bash read file into a bash script ( not line by line)
# bash ps format ps command to get pid
# bash how  much time did a bash command take
# bash read in a file in bash
# bash setting any program as a service
# bash check if port is being forwarded or not
# bash list all py files in a folder and open them side by side in vim
# bash find 2 lines that both start with #
# bash find if the first character of line is a #
# bash what does $* mean 
# bash sed awk in bash
# bash if element in array 
# bash rules about input arguments in bash: $* number of arguments, all arguments etc
# bash inherit variables from parent but dont modify parent shell
# bash collect all command line arguments into a function and if no argument is given take default arguments
# bash encrypt files to add the key or token, and unencrypt them to run
# bash remove the first element of the array
# bash locally modifying a global variable 
ar=(1 2)
f2(){ 
    echo "${ar[@]}" 
} 
f(){
    # make a local copy of the array
    local ar=("${ar[@]}")
    ar+=(3)
    echo "${ar[@]}"
    f2
}
echo "${ar[@]}"
# 1 2
f

# 1 2 3
# 1 2 3
echo "${ar[@]}"
# 1 2
# git unstage a file
git reset -- <filepath>
# SF git see previous commiteed version of a file
# git undelete a file
git checkout -- setup.py
# vim get output of last bash command to paste into vim
:r !ret
# analyze code to see which breakpoints are actually active?
#how to run an alias on a remote computer after ssh
#load vim buffers from file. e.g. tags for vimtodo2
#apt-key add?
#torun bash commands with bashrc sourced
bash -i -c "command"
# attack this domain to get the papers https://cmsworkshops.com/ICIP2024/Papers/Uploads/Proposals/PaperNum/1737/20240212050454_734992_1737.pdf
#what are certificates for https?
#grep and sed work on files, to make them deal with strings you need to do something else
#use cut for delimiter and for fields,id of the cut out part
#vim custom syntax
https://superuser.com/questions/844004/creating-a-simple-vim-syntax-highlighting
#in vim what is ctermfg and guifg
#in vim what does match do, why did it not work with syntax match
#in vim how do i define the syntax for a custom file
#vim autocmd
#vim BufRead, BufNewFile
#vim goto end of indented block
#difference between cterm and gui https://stackoverflow.com/questions/60590376/what-is-the-difference-between-cterm-color-and-gui-color
# gpg signing
# Mar Asia 4 --remove-source-files for remove the source files when doing rsync
# find <source_directory> -type d -empty -delete
# restore program https://www.xmodulo.com/how-to-checkpoint-and-restore-linux-process.html
# compiling latex on terminal: 
pdflatex abc.tex 
bibtex abc
#17 Mar 2024 11:01:56 regex match characters but not other characters
#19 Mar 2024 11:15:35 resizebox for resizing latex equations
https://tex.stackexchange.com/questions/237046/resizebox-within-equation-environment
#23 Mar 2024 21:43:04 
# send a command to all tty
https://unix.stackexchange.com/a/42368
for tty in /dev/pts/*; do clear > "$tty"; done # Linux (Ubuntu, via SSH)
pdflatex abc
# tmux ctrl arrow problems
https://superuser.com/questions/1621280/what-does-ctrlarrow-do-in-vim-within-tmux-and-how-do-i-skip-words
# pytorch out of memory error pytorch_cuda_alloc_conf
PYTORCH_CUDA_ALLOC_CONF=max_split_size_mb:512
# bash here doc 
# bash ls dir1/{subdir1,subdir1} and ls dir2 together
# which git commands require --
# - SF ERC exclude directories from rclone
# SF,ERC github see against file in previous commit
# 29 Apr 2024 07:45:37 check if key in bash dictinonary
# 29 Apr 2024 07:45:51 check if key exists in bash dictionary
# 05 May 2024 14:46:35 bash default value as an array
# 09 May 2024 15:50:47 multiple paste buffers in vim
# 12 May 2024 12:05:12 get signature of a function
inspect.signature(foo)
#12 May 2024 21:42:49 git rm does not delete the directory, only seems to remove it from the index
#14 May 2024 09:55:08 staticmethod __get__ TypeError: staticmethod object is not callable

# Debugging multiprocessing
1. disable cpu_count by patching it, so that if processes are started with cpu_count, then we can limit them to 1
2. check where multiproc is being used to create a pool, or process, and ensure those lines use cpu_count
# what is fork and spawn in multiprocessing
# debugging multiprocesing
https://stackoverflow.com/a/74225580


If you are trying to debug multiple processes running simultaneously, as shown in your example, then there's no obvious way to do that from a single terminal: which process should get the keyboard input? Because of this, Python always connects sys.stdin in the child process to os.devnull. But this means that when the debugger tries to get input from stdin, it immediately reaches end-of-file and reports an error.

If you can limit yourself to one subprocess at a time, at least for debugging, then you could get around this by setting sys.stdin = open(0) to reopen the main stdin, as described here.

But if multiple subprocesses may be at breakpoints simultaneously, then you will need a different solution, since they would all end up fighting over input from the single terminal. In that case, RemotePdb is probably your best bet, as described by @OnionKnight.
#Remote pdb
https://stackoverflow.com/questions/11106000/python-multiprocess-debugging
# SF vim search for line under cursor

#15 May 2024 17:23:47 what is virtual x server xvfb
#downloading form onedrive https://stackoverflow.com/questions/62634214/how-to-download-protected-files-from-onedrive-using-wget
# vim read only mode
vim -R # is readony
vim -M # sets modifiable off
# delete all blank lines vim
:g/^$/d
g runs a command globally
#pylint for only NameErrors
pylint --disable=all --enable=undefined-variable,import-error try_dff.py
# inspect get file of a funciton
inspect.getfile(some_func)
# python tracewith ignore
python -m trace --ignore-dir=$(python -c 'import sys ; print ":".join(sys.path)[1:]') -t ./script.py
# bash login files
https://www.baeldung.com/linux/bashrc-vs-bash-profile-vs-profile
# Banner
/etc/banner
# bash rerun last command ( use fl with fzf)
$(!!)
# vim disable jump on search
https://stackoverflow.com/questions/4256697/vim-search-and-highlight-but-do-not-jump
# grep invert
grep -v
# grep regex
grep -E -i 'foo|bar'
# conda clean
conda clean --all
# pip remove cache
pip cache purge
