### 环境配置

* 安装mingw 并配置好环境变量

* vscode codeRunner配置中不生成.exe文件

  * 插件配置中

    ```c
            // "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
            "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt && rm $dir$fileNameWithoutExt.exe",
            
                    // "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
            "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt && rm $dir$fileNameWithoutExt.exe",
    
    ```

  * 勾选

     Run In Terminal
     Save All Files Before Run

