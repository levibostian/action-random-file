# action-random-file

Create a file into a random path. 

# Getting started 

1. Install the GitHub Action into your workflow: 

```yml
jobs:
  main:
    # Action tested on ubuntu and macos
    runs-on: ubuntu-latest 
    steps:      
    - uses: levibostian/action-random-file@main
      id: create-file
      with:
        base64-file-content: ${{ secrets.BASE64_FILE_CONTENT }}
        file-name: "foo.txt"
    - name: Now, you can use the file! 
      run: ./use-file ${{ steps.create-file.outputs.path }}    
```

2. Create the secret in your GitHub repository. **Important: remove all `\n` characters from the base64 string.**
