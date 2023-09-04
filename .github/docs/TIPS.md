# Tips & Tricks

### How to determine if a file exists within a GitHub Action

So, you need to write a conditional statement in a GitHub Action which tests whether or not a file or files exist within the current repository:

```shell
	- name: Check File Exists
		id: check-files
		uses: andstor/file-existence-action@v1
		with:
		    files: "Dockerfile, README.md"

	- name: File Exists
		if: steps.check-files.outputs.files_exists == 'true'
		run: |
		...
```