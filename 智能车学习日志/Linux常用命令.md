# Linux常用命令
   - ls - 列出目录内容
   ```
    ls -alh
   ```
   注：ls是 "list" 的缩写。
   -cd - 更改目录
   ```
    cd /home/user/Documents
   ```
    注：cd是 "change directory" 的缩写。

   - pwd - 显示当前目录路径
    ```
     pwd
    ```
    注：pwd是 "print working directory" 的缩写。
   - cp - 复制文件或目录
    ```
     cp source.txt destination.txt
    ```
     注：cp是 "copy" 的缩写。
   mv - 移动或重命名文件或目录
    ```
     mv oldname.txt newname.txt     #这个是重命名
     mv file.txt /home/user/Desktop/ #这个是移动文件
    ```
     注：mv是 "move" 的缩写。
   - rm - 删除文件或目录
    ```
     rm file.txt
     rm -r directory/  #删除目录及其内容
    ```
     注：rm是 "remove" 的缩写。
   - mkdir - 创建新目录
    ```
     mkdir new_directory
    ```
     注：mkdir是 "make directory" 的缩写。
   - rmdir - 删除空目录
    ```
     rmdir empty_directory
    ```
     注：rmdir是 "remove directory" 的缩写。
   - touch - 创建空文件或更新文件的访问和修改时间
    ```
     touch newfile.txt
    ```
     注：touch的意思是“触摸”。
   - cat - 显示文件内容
    ```
     cat file.txt
    ```
     注：cat是 "concatenate" 的缩写。
   - more/less - 分页显示文件内容
    ```
     more file.txt
     less file.txt
    ```
     注：more和less都是用于分页查看文件内容的命令，less功能更强大。
   - find - 查找文件或目录
    ```
     find /path/to/search -name "filename.txt"
    ```
     注：find的意思是“查找”。
   - grep - 在文件中搜索文本模式
    ```
     grep "search_term" file.txt
    ```
     注：grep是 "global regular expression print" 的缩写。
   - chmod - 更改文件或目录的权限
    ```
     chmod 755 script.sh
    ```
     注：chmod是 "change mode" 的缩写。