<p align="center">
    <img width=100% src="/assets/cover.png">
  </a>
</p>
<p align="center"> 🤖 A de-obfuscation tool for Android APKs. Allowing you to compare multiple versions of an APK to identify the same code across renamed, altered, and missing functions. 📱 </p>

<br>

Obfu[DE]scate is a Python tool designed to take two versions of an APK file and use fuzzy comparison logic to identify similarities between functions even if they've been renamed as part of obfuscation. 
- To get started, download the dependancies and ensure you have APKTool installed and on your path.
- Get two versions of an APK and run ```ObfuDeScate.py``` with then as paramiters (use ```--apk_file_path_1``` and ```--apk_file_path_2```).
- After run, an ouput directory will be created with a mapping text file and full breakdown HTML file.

# ➡️ Getting Started 
## Installation 
After cloning the repository all Obfu[DE]scate dependencies can be installed manually or via the requirements file, with:

``` bash
pip install -r REQUIREMENTS.txt
```

In addition to the above, you will also need a copy of APKTool either on your path or provided with the ```--apk_tool_path``` paramiter. Download APKTool for your system as directed on [their website](https://ibotpeaches.github.io/Apktool/).

Obfu[DE]scate has only been tested on **Windows 11**, however, should work with other systems. 

## Options
Obfu[DE]scate takes the following paramiters:

| Shorthand | Paramiter         | Description                                                                                                                                            | Required |
|-----------|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
| -a1       | apk_file_path_1 | The path to the original APK. This is the APK that the second APK will be compared against (i.e. an older version of the APK)                          | True     |
| -a2       | apk_file_path_2 | The path to the newer APK. The output will show name changes between APK 1 and this APK.                                                               | True     |
| -cp       | class_path      | A reverse domain notation path that will be used to filter reviewed functions (i.e. provide com.example.class to only compare functions on this path). | False    |
| -o        | output_dir      | A directory to save the output mapping, html, and dissasembled APKs to.                                                                                | False    |
| -apktool  | apk_tool_path   | If APKTool is not on your path use this parameter to tell ObfuDeScate where APKTool is located.                                                        | False    |

## Running
The quickest way to use Obfu[DE]scate is to provide it with two APK files and a class path to compare. Providing a class path will drastically improve the comparison time and will limit it to only the class functions you care about. See below:

```bash 
python ObfuDeScate.py -a1 "old_example.apk" -a2 "new_example.apk" -cp "com.example.path"
```
In the above example Obfu[DE]scate will review all functions in the ```old_example.apk``` APK at the class path ```com.example.path``` and will compare them against all functions found at the same class path in ```new_example.apk```. 

# 🔎 Outputs
Obfu[DE]scate creates two output files, a mapping new line seperated list and an interactive HTML file. Examples of these can be found below:

<br>
<p align="center">
  <img src="/assets/html_example.png" width="500" />
  <img src="/assets/mapping_example.png" width="500" />
</p>
<br>
