## commands 

![[Git/branch]]
### stash 

`git stash` is a command that allows you to temporarily save changes that you have made to your working directory but do not want to commit yet. This is useful when you are in the middle of working on something, and need to switch branches or attend to some other task.

Here are some common `git stash` commands:

1. **Save your changes to a new stash:**

```
git stash save "Your stash message"
```

2. **List all stashes:**

```
git stash list
```

3. **Apply a specific stash (by index):**

```
git stash apply stash@{index}
```

4. **Apply the latest stash:**

```
gitstash apply
```

5. **Drop a specific stash (by index):**

```
gitstash dropstash@{index}
```

6. **Drop the lateststash:**

``` 
gitstash drop
```

7. **Pop a specificstash (apply and remove it from the list):**

``` 
gitstash pop stash@{index}
```

8. **Pop the lateststash:**

``` 
gitstash pop
```

9. **Create a new branch and apply a specificstash (by index):**

``` 
gitstash branch new_branch_name stash@{index}
```
