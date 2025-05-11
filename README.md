# Build ： Preprocess -> Compile -> Assemble -> Link
![屏幕截图 2025-05-08 014830](https://github.com/user-attachments/assets/30f67f40-d342-4275-a682-4b7156aacc0c)


### 1.Preprocess
> .cpp--------->.I  

Cpp files translated into the preprocessed source code

The pre-processor handle all directive like #include and #define,copying the contents of include header files into the source code file. 
 
If the files also have includes,they need copy their contents again.  

So **the more includes,the more overhead,the longer build time**.

### 2.Compile
> .I--------->.ASM  

The preprocessed source code translated into assembly language for the target platform

The compiler check the code syntax,usages of variables and functions,and so on.  

**This is the most frequent source of errors when building**.

### 3.Assemble
> .ASM--------->.OBJ  

The assembly code translate into machine code,producing an object file for the target platform

## Tips

`This three stages are run for every single source code file in order to generate an object file for each one in program，so that's why a build can take a long time.`  

**`But the process is incremental and runs on every single file，if one file changes,there're no need to rebuild the entire project.`**

`By the way,submit a change in Engine,that's need to rebuild the engine,because this change file may be widely cited.`

### 4.Link

