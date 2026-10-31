testfolder
----------
Sample output from the practice playbooks in ../playbooks:
  run_shell_commands.yml
  run_shell_commands_remote.yml

What those playbooks do with this folder:
  1. Create the folder 'testfolder' (shell: mkdir)
  2. Create 'newfile.txt' inside it (shell: touch)
  3. Add the line "Hi I'm your friend" to the file (lineinfile)
  4. Rename 'newfile.txt' to 'oldfile.txt' (shell: mv)

The 'creates:' option on each task makes the playbook safe to run again
(a task is skipped if its result already exists).

The two .txt files here were left behind by test runs. They are kept as
an example of what the playbooks produce. Delete the folder before a new
run if you want to see every task execute again.
