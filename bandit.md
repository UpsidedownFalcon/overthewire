# bandit 

- In command prompt (CMD)
- Must ```logout``` after completing each level
- SSH back into the new level e.g for level X, SSH into banditX at bandit.labs.overthewire.org port 2220

--- 

## Level 0 
```
ssh bandit0@bandit.labs.overthewire.org -p 2220 
bandit0
```

---

## Level 0 -> Level 1
```
cd 
ls
nano readme
```

> password for bandit1 = ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If 

---

## Level 1 -> Level 2
```
cd 
ls 
cat ./-
```

> password for bandit2 = 263JGJPfgU6LtdEvgfWU1XP5yac29mFx 

---

## Level 2 -> Level 3
```
cd 
ls 
cat ./"--spaces in this filename--"
```

> password for bandit3 = MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx 

--- 

## Level 3 -> Level 4 
```
cd ./inhere 
ls 
find 
cat ./...Hiding-From-You 
```

> password for bandit4 = 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ 

---

## Level 4 -> Level 5 
```
file ./-file0X 
- -file07 was the only ASCII text file
- 
cat ./-file07
```

To look through all files at once in `~/inhere/`: 
```
find . -type f -exec file {} +
```
where 
- `find .` recursively lists every file and directory inside the working directory
- `-type f` targets only files, skipping directory names
- `-exec` instructs to execute the following command for every single file recursively found previously
- `file` command to check the file type
- `{}` is a placeholder for the discovered file paths
- `+` bundles multiple files together into a single invocation of the `file` command

> password for bandit5 = 6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG

---

# Level 5 -> Level 6 
```
ls
cd inhere
ls
find .                           # recursively lists every file + directory from current working directory
find . -type f                   # recursively lists everything that is only the type file from current working directory
find . -type f -size 1033c       # recursively everything that is only a file + 1033 bytes in size from current directory
find . -type f -size 1033c -exec file {} +
cat ./maybehere07/".file2"
```

> password for bandit6 = pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

--- 

# Level 6 -> 7 
```
cd /                                                        # root of the server
find . -type f -user bandit7 -group bandit6 -size 33c       # find all in the working directory that is a file + owned by user bandit7 + owned by group bandit6 + 33 bytes in size
cat ./var/lib/dpkg/info/"bandit7.password"
```

> password for bandit7 = Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

--- 










