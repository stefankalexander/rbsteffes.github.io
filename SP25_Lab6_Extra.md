# Lab Step Guidance

# STEP 1 (Git command line and GitHub Desktop):

- **Find the Repository URL on GitHub**
  1. **Go to GitHub**  
       - Open a web browser and go to your repository:  
   👉 [https://github.com/studentwtcc/studentwtcc.github.io](https://github.com/studentwtcc/studentwtcc.github.io)

  2. **Locate the Clone Button**  
      - On the repository page, find the green **"Code"** button near the top right.

  3. **Copy the Clone URL**  
      - In the dropdown, you’ll see options like:
        - **HTTPS:** `https://github.com/studentwtcc/studentwtcc.github.io.git`

- **Why is This URL Important?**
  - This URL tells Git where to **fetch** (pull) and **push** (upload) changes.
  - When you run:
    ```bash
    git clone https://github.com/studentwtcc/studentwtcc.github.io.git
    ```
    Git:
    - Downloads the repository's contents.
    - Creates a folder named `studentwtcc.github.io`.
    - Sets up a connection between your local copy and the remote repository.


- **How to Check the Remote URL in an Existing Git Repo**
If you already cloned the repo, you can verify the remote URL by running:

    ```bash
    git remote -v
    ```

    This should output something like:

    ```
    origin  https://github.com/studentwtcc/studentwtcc.github.io.git (fetch)
    origin  https://github.com/studentwtcc/studentwtcc.github.io.git (push)
    ```

## Detailed steps for **cloning `studentwtcc.github.io`** using **Git command line** and **GitHub Desktop**.


- **Method 1: Using Git Command Line**
  - **Open Terminal or Command Prompt**
     - On **Windows**: Open **Git Bash** or **Command Prompt**.
     - On **macOS/Linux**: Open **Terminal**.

  - **Navigate to the Directory Where You Want to Clone**
    - Use the `cd` (change directory) command to move to the location where you want to clone the repository.

      Example:
      ```bash
      cd ~/Documents/GitHub
      ```
      or
      ```bash
      cd C:\Users\YourUsername\Documents\GitHub
      ```

      - **Clone the Repository**
      Run the following command:

      ```bash
      git clone https://github.com/studentwtcc/studentwtcc.github.io.git
      ```

      This will:
      - Download the repository to your computer.
      - Create a folder named **`studentwtcc.github.io`** in the current directory.

  - **Navigate into the Cloned Repository**
    - After cloning, move into the repository folder:

        ```bash
        cd studentwtcc.github.io
        ```

  - **Verify the Clone**
      Run the following command to check the status of the repository:

      ```bash
      git status
      ```
  If everything is correct, Git should show that you are on the **main** branch (or `master` if the repository uses the older default branch name).

---

- **Method 2: Using GitHub Desktop**

  - **Open GitHub Desktop**
  If you don’t have it installed, download and install it from [GitHub Desktop](https://desktop.github.com/).

  - **Click "Clone a Repository from the Internet"**
    - On the **main screen**, click **"Clone a repository from the internet"**.
    - Alternatively, go to **File** → **Clone Repository**.

  - **Find the Repository**
    - In the **"GitHub.com"** tab, search for **`studentwtcc.github.io`**.
    - If the repository does not appear automatically, click **"URL"** and enter:
      ```
      https://github.com/studentwtcc/studentwtcc.github.io.git
      ```

  - **Choose a Local Folder**
    - Select a location on your computer where you want to store the repository (e.g., `Documents/GitHub`).
    - Click **Clone**.

  - **Open the Repository**
    - Once cloned, GitHub Desktop will open the repository.
    - You can now view the files and commit changes.


**After Cloning**
Once the repository is cloned, you can:
- **Pull the latest changes**:  
  ```
  git pull origin main
  ```
- **Make and commit changes** using `git add`, `git commit`, and `git push`.
  
- **Push changes back to GitHub** using:
  ```
  git push origin main
  ```
- **Use GitHub Desktop** to commit and sync changes visually.

----------
# STEP 2:
The command:

```bash
git checkout -b lesson7
```

**What It Does**
  1. **Creates a new branch named `lesson7`** – The `-b` flag tells Git to create a new branch.
  2. **Switches to the newly created branch** – After running this command, `lesson7` becomes the active branch.

**Breaking It Down**
- `git checkout` – The command to switch branches.
- `-b` – A flag that tells Git to create a new branch before switching.
- `lesson7` – The name of the new branch.

**Example Workflow**
```bash
git checkout -b lesson7  # Create and switch to lesson7
git branch               # List branches (lesson7 should be active)
```

### **Alternative (Modern Git)**
Since Git 2.23, it's recommended to use:
```bash
git switch -c lesson7
```
This achieves the same result but is more explicit in intent.

# Step 3
Creating an **HTML file** in **VS Code** step-by-step guide:


- **📌 Manually Create an HTML File**
  - **Open VS Code**
  - Launch **Visual Studio Code**.

- **Open or Create a Project Folder**
  - Click on **File > Open Folder** and choose (or create) a folder where you want to store your HTML file.

- **Create a New HTML File**
  - In the **Explorer Panel (left sidebar)**, click the **New File** button (📄 icon) OR press:
    ```
    Ctrl + N (Windows/Linux)
    Cmd + N (Mac)
    ```

  - Name the file **`lesson7.html`** (or any other name ending in `.html`).

- **Save the File**
  - Press **`Ctrl + S`** (Windows/Linux) or **`Cmd + S`** (Mac) to save.

# STEP 4
## **1️⃣ `git add lesson7.html`**
```bash
git add lesson7.html
```
This command **stages** the file `lesson7.html`, meaning:
- Git starts tracking changes for `lesson7.html`.
- The file is prepared to be included in the next commit.
- It **does not save** the file permanently yet—just marks it for inclusion.

👉 **Alternative:** To stage **all** modified and new files, you can use:
```bash
git add .
```
(This adds all changes in the repository.)

---

## **2️⃣ `git commit -m "Added lesson7.html file"`**
```bash
git commit -m "Added lesson7.html file"
```
This command **saves the staged changes** (from `git add`) into Git’s history. Here’s what happens:
- Git creates a **commit**, capturing the changes in `lesson7.html`.
- The `-m "message"` option provides a commit message explaining the change.
- This commit is now stored locally, but **not yet pushed** to GitHub.

👉 **Good Commit Message Practices:**
- Keep it **short and descriptive** (e.g., `"Fixed bug in login page"`).
- Use the **imperative tense** (e.g., `"Add feature"` instead of `"Added feature"`).

---

# STEP 5

```bash
git push -u origin lesson7
```

### **What It Does**
1. **`git push`** – Pushes your local changes to the remote repository.
2. **`-u` (or `--set-upstream`)** – Sets `origin lesson7` as the upstream branch for the local `lesson7` branch. This means future `git push` and `git pull` commands will automatically refer to `origin lesson7` without needing to specify the branch explicitly.
3. **`origin`** – The name of the remote repository (default name when you clone a repo).
4. **`lesson7`** – The branch being pushed to the remote repository.

### **When to Use This Command**
- If `lesson7` is a new branch that hasn’t been pushed before.
- If you want to establish an upstream connection so that future `git push` and `git pull` commands work without specifying the remote and branch.

### **Example Workflow**
```bash
git checkout -b lesson7  # Create and switch to new branch
git add .                # Stage changes
git commit -m "Initial commit for lesson7"  # Commit changes
git push -u origin lesson7  # Push to remote and set upstream
```

After this, future pushes and pulls can be done simply with:
```bash
git push
git pull
```
Since the upstream is now set, Git knows where to push/pull automatically. 🚀

# STEP 6
## **Merging Branches Using Git and GitHub**
Here’s how to merge branches using **Git command line** and the **GitHub web interface**.

---

## **🔹 Method 1: Merge Using Git (Command Line)**
### **Step 1: Switch to the Target Branch (Usually `main` or `master`)**
Before merging, switch to the branch where you want to apply the changes:

```bash
git checkout main  # Or git checkout master
```

### **Step 2: Pull the Latest Changes (Optional but Recommended)**
Ensure your local `main` branch is up to date with the remote repository:
```bash
git pull origin main
```

### **Step 3: Merge the Feature Branch into `main`**
Now, merge your feature branch (e.g., `lesson7`) into `main`:

```bash
git merge lesson7
```

- If Git merges automatically, you will see a success message.
- If there are conflicts, Git will notify you to resolve them.

### **Step 4: Push the Merged Changes to GitHub**
After merging locally, push the updated `main` branch to GitHub:

```bash
git push origin main
```

---

## **🔹 Method 2: Merge Using GitHub Web Interface**
### **Step 1: Go to Your Repository on GitHub**
1. Open **[GitHub](https://github.com/)**.
2. Navigate to your repository (e.g., `studentwtcc.github.io`).

### **Step 2: Open the "Pull Requests" Tab**
1. Click on the **Pull Requests** tab.
2. Click **New Pull Request**.

### **Step 3: Choose Branches to Merge**
1. Select the **base branch** (e.g., `main`).
2. Select the **compare branch** (e.g., `lesson7`).
3. GitHub will show the differences between the branches.

### **Step 4: Create a Pull Request**
1. Click **Create Pull Request**.
2. Add a meaningful title and description.
3. Click **Submit**.

### **Step 5: Merge the Pull Request**
1. Once the pull request is created, you (or a collaborator) can review it.
2. Click **Merge Pull Request**.
3. Choose a merge method:
   - **"Merge commit"** (default) – Keeps all commits separate.
   - **"Squash and merge"** – Combines all changes into one commit.
   - **"Rebase and merge"** – Rewrites commit history (advanced).

4. Click **Confirm Merge**.

# STEP 7
Let's break down each command and explain what it does:

---

### **1️⃣ `git checkout main`**
```bash
git checkout main
```
👉 **Switches to the `main` branch** (or `master` if that's the default branch).

- Before deleting a branch, you **must not be on that branch**.
- This command ensures that you're on `main` before removing `lesson7`.

**Alternative (Modern Git)**  
Since Git 2.23+, it's recommended to use:
```bash
git switch main
```

---

### **2️⃣ `git branch -d lesson7`**
```bash
git branch -d lesson7
```
👉 **Deletes the local branch `lesson7`**.

- The `-d` flag ensures the branch is **only deleted if it is fully merged** with the current branch (`main`).
- If the branch is not merged, Git will show an error to prevent accidental deletion.

**For Force Deletion:**  
If you **haven’t merged** `lesson7` yet but still want to delete it, use:
```bash
git branch -D lesson7
```
⚠️ **Warning:** This permanently deletes the branch locally, losing any unmerged changes.

---

### **3️⃣ `git push origin --delete lesson7`**
```bash
git push origin --delete lesson7
```
👉 **Deletes the remote branch `lesson7` on GitHub**.

- Even after deleting `lesson7` locally, it still exists on GitHub (or another remote repository).
- This command **removes it from GitHub** so others don’t see it anymore.

---

### **📌 Full Workflow Example**
```bash
git checkout main          # Switch to main branch
git pull origin main       # Get the latest changes (optional but recommended)
git branch -d lesson7      # Delete the local lesson7 branch
git push origin --delete lesson7  # Delete the remote lesson7 branch
```

---

### **📝 Summary of Commands**
| Command | What It Does |
|---------|-------------|
| `git checkout main` | Switches to the `main` branch |
| `git branch -d lesson7` | Deletes the **local** `lesson7` branch (only if merged) |
| `git push origin --delete lesson7` | Deletes the **remote** `lesson7` branch on GitHub |

---

### **🚀 Why Do This?**
- **Keeps the repository clean**: No need to keep old feature branches after merging.
- **Prevents confusion**: Team members won’t see outdated branches.
- **Saves space**: GitHub has a limit on the number of branches per repo.


