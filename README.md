# 0x03 - Shell Variables & Expansions (Windows + VS Code + WSL Setup)

This project contains a set of Bash scripts that explore shell variables, environment variables, expansions, and simple arithmetic in Bash.

The recommended setup is **Windows 10/11 with WSL (Ubuntu)** and **Visual Studio Code** with the **Remote - WSL extension**.

---

## 🚀 Quick Setup (Windows + VS Code)

### 1. Install WSL + Ubuntu

Open **PowerShell (Admin)** and run:

```powershell
wsl --install -d Ubuntu-20.04
If wsl --install is not available, follow Microsoft’s WSL installation guide.

After installation, open the Ubuntu terminal and set your username and password.

2. Install VS Code & Remote - WSL
Download and install Visual Studio Code.

In VS Code, install the Remote - WSL extension.

Open a new WSL session:

Press Ctrl+Shift+P → type Remote-WSL: New Window.

This opens VS Code attached to your Ubuntu filesystem.

3. Clone the Repository
In your WSL terminal (or VS Code terminal set to WSL):

bash
Copy code
cd ~
git clone https://github.com/<your-fork>/alx-system_engineering-devops.git
cd alx-system_engineering-devops/0x03-shell_variables_expansions
Replace <your-fork> with your fork/username.

4. Create Scripts & Make Them Executable
Inside 0x03-shell_variables_expansions, create each file using VS Code.
After saving, run:

bash
Copy code
chmod +x 0-alias 1-hello_you 2-path 3-paths 4-global_variables \
  5-local_variables 6-create_local_variable 7-create_global_variable \
  8-true_knowledge 9-divide_and_rule 10-love_exponent_breath \
  11-binary_to_decimal
⚠️ Important Safety Note (Task 0)
Task 0 (0-alias) creates an alias ls → rm *.
This will delete files when you run ls.

✅ Always test in a temporary folder (e.g., /tmp/0x03).
✅ To bypass alias: use \ls or /bin/ls.
✅ To remove alias: unalias ls.

📜 Scripts (0 → 11)
Each script starts with:

bash
Copy code
#!/bin/bash
0. 0-alias
bash
Copy code
alias ls="rm *"
Defines alias ls → rm *.
Safe test:

bash
Copy code
mkdir -p /tmp/0x03 && cd /tmp/0x03
touch file1 file2
source ~/alx-system_engineering-devops/0x03-shell_variables_expansions/0-alias
ls         # deletes file1 file2
\ls        # real ls
unalias ls
1. 1-hello_you
bash
Copy code
echo "hello $USER"
Prints: hello <username>

2. 2-path
bash
Copy code
export PATH="$PATH:/action"
Appends /action to $PATH.

3. 3-paths
bash
Copy code
echo "$PATH" | tr ':' '\n' | wc -l
Counts directories in $PATH.

4. 4-global_variables
bash
Copy code
printenv
Lists all environment variables.

5. 5-local_variables
bash
Copy code
set
Lists all shell variables + functions.

6. 6-create_local_variable
bash
Copy code
BETTY="I am local"
Creates a local (non-exported) variable.
Persists only if sourced.

7. 7-create_global_variable
bash
Copy code
export HOLBERTON="HolbertonSchool"
Creates an exported (global) variable.

8. 8-true_knowledge
bash
Copy code
echo $((128 + ${TRUEKNOWLEDGE}))
Adds 128 to $TRUEKNOWLEDGE.

9. 9-divide_and_rule
bash
Copy code
echo $(( POWER / DIVIDE ))
Divides $POWER by $DIVIDE.

10. 10-love_exponent_breath
bash
Copy code
echo $(( BREATH ** LOVE ))
Raises $BREATH to the power of $LOVE.

11. 11-binary_to_decimal
bash
Copy code
echo "$((2#$BINARY))"
Converts binary in $BINARY to decimal.

🧪 Testing Workflow
Open a WSL terminal in VS Code (Terminal → New Terminal).

Run chmod +x <file> before executing.

Test in a safe folder (e.g., /tmp).

If script depends on environment variables, set them first:

bash
Copy code
export BINARY=1010
./11-binary_to_decimal   # → 10
To bypass alias:

bash
Copy code
\ls
/bin/ls
To remove alias:

bash
Copy code
unalias ls
```
