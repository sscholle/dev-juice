### Git Config
- file: ~/.gitconfig
#### Description
Configure global git settings 
#### Example Code
```
[core]
    ...
	editor = code --wait
...
[user]
	name = Your Full Name
	email = Your@email.com
[commit]
	template = /path/to/template/file
```
#### Notes
core -> editor describe the app used to make changes to Commits via rebasing and other functions. By using 'code' app we have a familiar editing environment