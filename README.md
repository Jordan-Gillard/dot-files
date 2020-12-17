# Jordan's Dot Files
This repository is used to store my dot files. These files contain 
configurations and custom functions, and not private stuff like API keys.

### Contributing
Contributions are welcome! If you can simplify a shell script, then by all
means, feel free to leave these files cleaner than you found them. It is
definitely appreciated.

### Notes on usage
If you want to do something similar to what I've done, you'll run into the 
problem of figuring out how to load the dot files from their directory into
your `.zshrc` file. If you have a lot of dot files (which you should have to 
keep everything separated), you'll want to load all dot files in your dot file
directory. I came up with the following script for doing so. This script loads
all dot files in the directory except for those that contain the string `.git`

```shell
source_dot_files()
{
for file in ~/YOUR-DOT-FILE-DIR-HERE/.*
do
    # Dont try and source git files
    if [[ "$file" != *".git"* ]]
        then source $file
    fi
done
}

source_dot_files
```

Put that script in the bottom of your `.zshrc` file, and substitute 
`YOUR-DOT-FILE-DIR-HERE` with your directory of dot files, and you should be
good to go.
