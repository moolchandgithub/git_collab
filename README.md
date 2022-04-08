# git_collab
Learning Git Collobration
- Git have three basic hash :
  - Blob
  - Tree
  - Commit

- `git clone <URL>`: "downloads" the git repository to current directory
    - `git init`: creates a git repo locally

- `git log`: Check git history
   -  $ git log --oneline --graph --all\
      \* e722522 (HEAD -> main, origin/main, origin/HEAD) Git Clone and init
      \* 3585699 README Updated
      \* 5ee047e Initial commit

- `git add`: Add file in git staging area
   - Git take the content of file and pass it to hashing algo, generate Hash value and save it in .git/objects/
   - It generate same hash for same content, no duplicate values

- `git cat-file -t <Hashvalue>`: To check type of hash.
   - git cat-file -t e722522\
     commit

- `git cat-file -p <Hashvalue>`: To read the content of file.
   - You can get hash value from git log command for respective commit.
   - From that output, you can pick tree hash and check which blobs/tree belong to that hash.
   - Using blob hash, you can check content of file.

- `git write-tree`: Records all attributes of file as below and hash it.
   - 100644 blob ca1029f14451d1d9b309752c2b210527d6866c09    README.md 
   - It generate hash and save it in .git/objects/
   - When you do git commit, it does write-tree in background automaticaly.

- `git commit`: Record root tree, commit message, author and committer details as below and hash it.
   - Git commits the entire tree per commit.
   - After first commit, all the commit will be having parent commit refrence hash.\  
       tree 86fddd1f568cd91058f1eea9f2637ad14b857105\
       parent 3585699de917c4ec35a227848b741b9e11f4d615\
       author Moolchand <mool.attrish@gmail.com> 1649149991 +0300\
       committer Moolchand <mool.attrish@gmail.com> 1649149991 +0300\
       Git Clone and init \
