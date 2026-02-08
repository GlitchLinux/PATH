**Usage examples:**

```bash
# Basic path resolution

PATH file.txt
# Output: /home/user/projects/file.txt

PATH /directory/
# Output: /full/path/to/directory/

PATH .
# Output: /current/working/directory/

PATH ~/Documents
# Output: /home/user/Documents/

PATH ../parent
# Output: /parent/directory/parent

# List mode

PATH --list /tmp/
# Creates: /tmp/path_list_tmp_20240115_143022.txt
# Prompts: Show list? [Y/n]

PATH --list .
# Creates list of all files in current directory

# Help
PATH -h
```

**Features:**

1. **Clean output** - Just the path, nothing else
2. **Directory formatting** - Automatically adds trailing `/` for directories
3. **Special path handling**:
   - `.` - Current directory
   - `..` - Parent directory  
   - `~` - Home directory
   - `~/path` - Path relative to home
4. **List mode** (`--list`):
   - Creates timestamped files in `/tmp/`
   - Shows first 50 entries when prompted with 'Y'
   - Includes metadata (date, total files)
   - Sorted alphabetically
5. **Error handling** - Shows clear error if path doesn't exist
6. **No dependencies** - Pure Python, works everywhere

**Example output:**

```bash
$ PATH .
/home/user/projects

$ PATH --list .
Created list of 147 files
List saved to: /tmp/path_list_home_user_projects_20240115_143022.txt

Show list? [Y/n]: Y

Files in '/home/user/projects/':
   /home/user/projects/.gitignore
   /home/user/projects/README.md
   /home/user/projects/config.json
   /home/user/projects/data/file1.csv
   /home/user/projects/data/file2.csv
   ...
   
... and 97 more files in the complete list

Full list available at: /tmp/path_list_home_user_projects_20240115_143022.txt
To view all: cat /tmp/path_list_home_user_projects_20240115_143022.txt | less
```
