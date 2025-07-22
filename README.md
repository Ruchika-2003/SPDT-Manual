    
# User Manual


## What does the tool do ?

The Software Plagiarism Detection Tool (SPDT) detects plagiarism in C++ code by analyzing structural similarity between submissions. It generates detailed reports with similarity percentages, clear conclusions, and visual comparisons using the GumTree Diff Tool. SPDT also supports customizable querying to filter results by group or similarity range, making large outputs easier to navigate. Additionally, it integrates with MOSS to extend detection to Lex and Yacc files for comprehensive assignment analysis.


## What does the tool work on ?
- Files
- Directories
- Single directory (with files or directory based submissions)  
The submissions accepts only (.cc/.cpp), (.h/.hh), .l, .y files.

## Tool Dependencies 
Below are the contents of requirements.txt which are needed to run the script without errors 

        clang==16.0.6
        zss==1.2.0
        prettytable==3.10.0
        requests==2.31.0
        dill==0.3.8

Run the following command :

        pip install -r requirements.txt

System level dependencies 

        sudo apt install llvm-18 libclang-18-dev default-jdk

        
## How to use the tool ?
1. ssh into the plagcheck by entering your credentials
![image](https://github.com/user-attachments/assets/cacfd55d-c3c5-42dd-849b-61b767fdd16e)
2. Enter the spdt directory where the tool is present (Make sure that the submissions that you want to check are present in the same directory where your tool is present)
3. Run the command below to use the tool

        For files :
        ./run_all.sh <file names or paths (2 or more)>

        For directories :
        ./run_all.sh <directory names or paths (2 or more)>

        For a single directory :
        ./run_all.sh <single directory name or path with submissions inside them>


## Expected outcomes
Below are some expectations with respect to the timings and other factors while running the tool on submissions :

1. For files :
<img width="1338" height="491" alt="image" src="https://github.com/user-attachments/assets/703d2541-2533-4066-b175-b94b30b13672" />

Opening the html file

<img width="1821" height="503" alt="image" src="https://github.com/user-attachments/assets/3c5a7a5a-1918-49c0-8011-bcddf712e4b9" />


- Time required :
For comparing two small (20-30 LOC) .cpp files time required is lesser than 1s.

- What does it work on ? :
(.cc/.cpp), (.h/.hh) files.

- Expected outcome :
The output will be saved in a designated directory and will include both a .txt and a .html file, which can be viewed to analyze the results. Additionally, you can query the output based on your preferences for more specific insights.

2. For directories :
<img width="800" height="596" alt="image" src="https://github.com/user-attachments/assets/61eefcf8-231e-42fa-8e84-05597e95087f" />

On opening the html file :


<img width="800" height="792" alt="image" src="https://github.com/user-attachments/assets/6de3fc46-0c6d-4913-84a8-1941958a44e6" />
<img width="800" height="431" alt="image" src="https://github.com/user-attachments/assets/20c598f5-6f01-44c0-8051-3c30d5854aab" />


- Time required :
For comparing two groups with combination of C++ and header files leading to almost 1000-1300 LOC, it takes about 4s.

- What does it work on ?
It works with files inside the directories being (.cc/.cpp), (.h/.hh), .y, .l

- Expected outcome :
The output will be saved in a designated directory and will include both a .txt and a .html file, which can be viewed to analyze the results. Additionally, you can query the output based on your preferences for more specific insights. If the directories contain lex yacc files too then the html output will have the tool's output along with the MOSS output run on them.


3. For a single directory :
<img width="800" height="700" alt="image" src="https://github.com/user-attachments/assets/9aaf3823-7ac1-476e-8966-8531dcc169c5" />

On opening html file :

<img width="800" height="811" alt="image" src="https://github.com/user-attachments/assets/8b5cda86-5233-4bbb-87c5-c1139080a7fd" />
<img width="800" height="857" alt="image" src="https://github.com/user-attachments/assets/c1950bec-c81b-43c3-ba1a-84ccc529e299" />

- Time required : For comparing a submission with 10 groups it takes about 2 minutes.
  
- What does it work on ?
It works on groups having (.cc/.cpp), (.h/.hh), .y, .l files inside them.

- Expected outcome :
The output will be saved in a designated directory and will include both a .txt and a .html file, which can be viewed to analyze the results. Additionally, you can query the output based on your preferences for more specific insights. If the directories contain lex yacc files too then the html output will have the tool's output along with the MOSS output run on them.


## Querying with single directory outputs :
<img width="800" height="718" alt="image" src="https://github.com/user-attachments/assets/c4d780b5-9d5a-45bb-b014-3925bcd9a017" />

<img width="800" height="480" alt="image" src="https://github.com/user-attachments/assets/32083369-0fff-467e-8746-dfecd5759960" />



Opening the saved .csv file (Stored the output of last performed query)

<img width="800" height="130" alt="image" src="https://github.com/user-attachments/assets/fa7355b6-f685-4135-8824-c17c9c93c8f0" />
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/905144b5-78b1-49e7-a598-5f6538be7f10" />


## Checking visual differences :

Use the link below :
http://cs316.cse.iitb.ac.in/spdt_check/

Go to the output directory for which you want to see the visual difference :
<img width="800" height="743" alt="image" src="https://github.com/user-attachments/assets/63ad2309-8b4e-4ecf-aeed-9442f32dfe5c" />

Open the combined output to get both the tool and moss's output together :

<img width="800" height="592" alt="image" src="https://github.com/user-attachments/assets/b0b5c8c6-56f6-4eab-a071-1a4d3056e870" />

On opening the html file :

<img width="800" height="675" alt="image" src="https://github.com/user-attachments/assets/6d6bc252-3104-4a0d-9c1f-cd8da2169e76" />

<img width="800" height="430" alt="image" src="https://github.com/user-attachments/assets/9ba1f385-6ddb-4824-baa4-ac81fb42b506" />

Opening the visual difference link :

<img width="800" height="860" alt="image" src="https://github.com/user-attachments/assets/e08bc7ca-0360-498a-8041-dabdb2b456be" />

You can view the differences between the compared code files, with syntax-based changes highlighted. To better understand the meaning of each color used in the highlights, please refer to the legend below.



<img width="220" height="215" alt="image" src="https://github.com/user-attachments/assets/0068455b-3113-4288-813d-70a6fc4c1f21" />


## What does the tool not do ?

- The tool is specially made for C++ submissions (including lex yacc files) and does not work in other cases
- You cannot specifically test just lex or yacc files they must be present with other C++ files for MOSS to effectively run on it

## Overall Tool Expectations :

- The tool takes in user-provided submissions to check and compare.
- The output can be queried based on user preferences to filter specific results.

- After processing, the output is stored in a designated directory, which contains:
  - A `.txt` summary file
  - An `.html` report

- The `.html` report includes:
  - Percentage similarity
  - Final conclusions
  - Links to visual code differences using the GumTree Diff Tool

- If the submissions include Lex/Yacc files, they are compared using **MOSS**, and the MOSS results are integrated into the same HTML report for a consolidated view.


## What can go wrong ?

- Sometimes MOSS fails due to connectivity issues and gives error like below
![moss_error](https://github.com/user-attachments/assets/ba4639b5-52fc-4c74-ab4e-5e6e640d5cbf)

In this case we must wait for a while until the error gets resolved by itself


---




# Developer Manual

## Introduction 

This tool aims to work on the syntactical difference between the source codes by using their Abstract Syntax Trees (ASTs), and further inculcates gumtree (a syntax aware diff tool) to provide visual insights into the differences in the source codes.

## Pre-requisites with version specifications

### 1. Gumtree - Syntax-aware diff tool

For more detailed installation refer : https://github.com/GumTreeDiff/gumtree/wiki/Getting-Started

- Clone this in your parent directory:

https://github.com/GumTreeDiff/gumtree

- Make sure the Java version is set to **Java 17** (Prerequisite for Gumtree).

- After cloning, follow the below commands:

        
      cd gumtree
      ./gradlew build
  
- Add the following to your .bashrc file and source it:

      export PATH=$PATH:/path_to_your_parent_directory/gumtree/dist/build/install/gumtree/bin
  
  Example:

      export PATH=$PATH:/home/plagcheck/spdt/gumtree/dist/build/install/gumtree/bin

- Now test by typing gumtree in your terminal. It should give output like:
  <img width="776" height="495" alt="image" src="https://github.com/user-attachments/assets/cd0122bd-6b3b-4a04-bb20-6693975267de" />

### 2. srcml - Requirement for obtaining visual differences

- Assumes you are using Ubuntu 20.04
- Run the following commands:

        wget -P srcml_req http://131.123.42.38/lmcrs/v1.0.0/srcml_1.0.0-1_ubuntu20.04.tar.gz
        cd srcml_req
        echo 'export PATH=$PATH:~/CS302/srcml_req/bin' >> ~/.bashrc
        echo 'export PATH=$PATH:~/CS302/srcml_req/lib' >> ~/.bashrc
        source ~/.bashrc
- Check if srcml was installed properly by verifying its version:

        srcml --version


After these requirements are satisfied, go to [Tool Dependencies](#tool-dependencies) and follow the steps to start using the tool.

## How does the tool deal with submissions ?

- With files :
  -    With files it preprocesses the source code followed by generating AST and then uses difflib to calculate the percentage similarity. (Difflib has the best time complexity to offer with respect to other options)

- With single or multiple directories :
    - In case of diretories which has (.cc/.cpp), (.h/.hh), .l, .y files in it, the tool takes care of the C++ submissions by combining the (.cc/.cpp) and (.h/.hh) files into a single file which is further             preprocessed and dealt with just like how files is as stated above.
    - We have further integrated MOSS to have a close look at the other files like .l, .y that the tool does not consider, this is done to not overlook any component of the directory

## Design Evolution / Implementation History

The SPDT tool was designed to detect structural similarities between C++ submissions using Abstract Syntax Trees (ASTs). Over time, as the size and complexity of submissions increased, the tool underwent several key design changes to improve scalability and performance.

---

### 🔹 Phase 1: AST Comparison Using ZSS (Zhang-Shasha Algorithm)

- **Initial Approach**:  
  The tool originally relied on the **Zhang-Shasha (ZSS)** algorithm to compute **tree edit distance** between ASTs generated from C++ source files.

- **Performance**:  
  - For small files (~100 LOC), ZSS worked well — giving results in under 3–4 seconds per comparison.
  - However, as the tool scaled to real-world CS302 submissions (often exceeding 1000 LOC), performance degraded sharply.
  - Comparing directories with multiple source/header files started taking **more than 2 minutes**, and often led to process termination due to excessive memory/CPU usage.

- **Reason**:  
  The theoretical **O(n²)** complexity of ZSS per pair of ASTs, combined with **O(k²)** for generating all file pairs (for `k` files), resulted in **O(k²n²)** time — making it infeasible for large datasets.

---

### 🔹 Phase 2: Switched to `difflib` for Scalable Comparison

- **Need for Change**:  
  Due to ZSS’s inefficiency at scale, a faster method was required — one that still respected structural similarity and was compatible with AST-based workflows.

- **New Approach**:  
  The tool was updated to use Python’s built-in `difflib` library, which operates with **O(n)** complexity (in practical scenarios) and performs fast sequence comparisons.

- **Impact**:
  - Dramatically improved performance and scalability.
  - Comparing 200 submissions, each with ~1000 LOC, now completes in under **1.5 hours**.
  - The quality of results remained consistent with the ZSS-based version, making `difflib` a viable and efficient replacement.

---

### Summary of Evolution

| Stage        | Method Used                 | Complexity          | Status                          |
|--------------|-----------------------------|---------------------|----------------------------------|
| Phase 1      | ZSS (Tree Edit Distance)    | O(k² × n²)           | Deprecated (Slow on large datasets) |
| Phase 2      | `difflib`  | ~O(n) in practice    | Adopted (Fast and scalable)       |


## Developed By

**Ruchika Shirsath**  
Under the guidance of **Dr. Uday Khedker**

For any queries, suggestions, or to report issues, feel free to reach out via email:  
*ruchikashirsath2003@gmail.com*














