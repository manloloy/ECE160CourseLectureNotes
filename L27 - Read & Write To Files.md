# Read and Write to files
-  in google collab path to sample data "/content/sample_data"
-  in google collab path to the content directory "/content"
- ./ or . usually means current directory
- ../ or .. is usually the previous directory

Google Collab
- clicking on the folder icon in the left bar shows the content directory.
- You can also connect collab to your google drive

Local Machine
- reading and writing files on your local machine behaves the same way.
- You just need to make sure that the path you are using is correct.

# Reading an entire file

If we want to read a file in python, use the open() function to open a file. This function returns a file object that has a few methods.


The open() function is built into the basic python3 installation and can be used without importing  any library.

Functions:
-open(string) -The open() built-in function requries a single argument that specifies the path to the file. You can use relative and full path strings.

Methods:
- file.read() - all file contents returned as a string
- file.readlines() - all file contents returned as a list of lines, where each line is a string
- file.close() - closes the open file

You should close the file when you do need the file anymore.



```python
# Before you run this code, there must be a file name file.txt in your content
# directory or change the path used below to point to the file you want to read
# the contents of. The file is shown below
'''
line 1
line 2
line 3
This is the last line in the file
'''

# open the file
f = open('/content/file.txt')
# print the file object
print(f, type(f))
# read the file contente
contents = f.read()
# close the file
f.close() # good practice to close when finished with the file

print(contents)
#print(type(contents))
#print('line 1\nline 2\nline 3\nThis is the last line in the file')
```

    <_io.TextIOWrapper name='/content/file.txt' mode='r' encoding='utf-8'> <class '_io.TextIOWrapper'>
    line 1
    line 2
    line 3
    This is the last line in the file



```python
# Using the same file, try file.readlines()
f = open('/content/file.txt')
contents = f.readlines()
f.close()
print(contents)
print(type(contents))
print(contents[1])
print('Interesting')
print(contents[1][0:-1])
print(contents[1].split('\n')[0])

for line in contents:
  print(line)

for line in contents:
  print(line, end='')
```

    ['line 1\n', 'line 2\n', 'line 3\n', 'This is the last line in the file']
    <class 'list'>
    line 2
    
    Interesting
    line 2
    line 2
    line 1
    
    line 2
    
    line 3
    
    This is the last line in the file
    line 1
    line 2
    line 3
    This is the last line in the file

# Writing to files
Files can be opened in different modes:

![Open() options table](https://raw.githubusercontent.com/manloloy/EE160Images/main/openoptionstable.png)

Method to write:
- file.write() -  the argument is any string. Use this like printing to the screen.


```python
# write to file
x = 5
y = 10
f = open('/content/file2.txt', 'w') # the file doesn't exist so it will be created
f.write(f"Line 1 x,y={x},{y}\nLine 2\nLine 3")
f.write("\nThis is another Line")
f.close()
# observe file2.txt
```


```python
[a, b] = [-5, 500]
f = open('/content/file3.txt', 'a') # the file doesn't exist so it will be created
f.write(f'a = {a}, b = {b}\nThis is the last line in the file.')
f.write(f'\nb={b}, a={a} - This is the real last line')
f.close()
# observe file3.txt
```


```python
# make sure the cell above was executed 1 time
f = open('/content/file3.txt', 'a') # the file does exist. It will not overwrite the original contents
f.write(f'\nJust kidding, this is the real last line')
f.close()
# observe file3.txt
```


```python
f = open('/content/file3.txt', 'w')
f.write(f'Is this overwritting?\n')
f.close()
# observe file3.txt
```
