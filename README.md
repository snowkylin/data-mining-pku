# Assignment of course "Data Warehousing and Data Mining Technology", Spring and Summer Semester, 2017.

## Projects Description

Project 1 & 2 are application-oriented. Project 3 & 4 are algorithm-oriented. You need to select **one** of these projects as your assignment.

### Project 1: Visualization of data distribution (updated on MySQL usage and UI)
- Dataset: [Bank Marketing Data Set](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing) (in FTP server)
- Your task: to build an application to show the distribution of attributes (dimensions) in the dataset.

#### Requirements

- Supportance of slice and dice operation
    - If I choose one or several values of specific attribute(s), the application should be able to show the distribution filtered by these values. 
    - For example, If I choose "age = 18-22 and job = student", you need to show the distributions of some other attributes (like education and balance) conditional upon "age = 18-22 and job = student".
    - If you can only implement slice operation on one attributes, that is acceptable but the score will be lower.
- Supportance of MySQL
    - Able to import the .csv data to MySQL database and load data from it.
    - **(updated)** You can assume that there is an empty database named "bank" with username "test" and empty password in the local MySQL database. This account have all privilege to manipulate the "bank" database.
- **(updated)** Interactive UI
    - Users without much programming knowledge can operate your application by select, click and other simple actions.
    - Web or desktop based UI is OK. Command-line interface is not acceptable.
- **(bonus point)** You will get more score if your application can support more OLAP operations, such as roll-up and drill-down.
- **(bonus point)** You will get more score if your application can handle time and date. (you need to provide some other time-related data to test this feature)

#### Suggestions (new)

- You may use Python (with matplotlib, mysqldb and so on) or PHP to build the application.
- If you choose PHP, [D3.js](https://d3js.org/), a really powerful tool for interactive data visualization, is recommmended as the front-end library.

### Project 2: Visualization of data correlation

The dataset and requirements are the same with project 1, but the task is to show the correlation of two selected attributes.

### Project 3: "Phrase" mining based on frequent patterns

- Dataset: 
    - [Gutenberg dataset](https://web.eecs.umich.edu/~lahiri/gutenberg_dataset.html) (in FTP server)
    - [Amazon review data](http://jmcauley.ucsd.edu/data/amazon/) (optional but recommended)
- Your task: design and implement a data mining algorithm to find the "phrase" in these texts based on frequent patterns.
- **(updated)** The "phrase" here is more general. Two words can be called "phrase" when they always appear together in one sentence (or paragraph, chapter, etc.), even if they are not adjacent. Sorry for this ambiguous point and thank @WillsNew.

#### Suggestions (new)

- The dataset is quite large. You may select **part of them** that you are interested in.
- **(bonus point)** You will get more score by applying your algorithm to other dataset (such as Amazon review data).
- **(bonus point)** You can see sentences as "baskets" as the slide says. However, I suggest you to try some different ways (and you will get more score), such as:
    - See paragraphs as baskets
    - See chapters as baskets
    - See books as baskets (this might be harder)
    - (For amazon review data) See reviews as baskets
- You may apply some "stop word" methods, which is common in NLP related tasks.
- You may use Python for data preprocessing. However, if you want to make you program more efficient, you may use c++ to implement the core algorithm.

### Project 4: Implementation of a "influential" data mining algorithm

- Your task: just as the title says.
- Prepare the dataset by yourself.
- Don't implement your algorighm by a single line with the help of library function, such as:
    - res = xxxlib.Apriori(data)
    - rank = xxxlib.PageRank(data)
- If you want to implement other algorithms, please post an issue in this repo.
- For the hard and extreme level, there is [a short summary](https://snowkylin.github.io/network-mining/heterogeneous-network/2017/04/25/heterogeneous-network-mining-index.html) of them. If you want to implement one of them, you are warmly welcomed to communicate with me (the teaching assistant) after reading the corresponding paper. Maybe I will give you some specific help depending on which paper you select.

#### Candidate choices (Normal)

- FP algorithm
- PageRank (at least 10000 nodes and 100000 edges)

#### Candidate choices (Hard, with at least 5 bonus point)

- RankClus
    - Y. Sun, J. Han, P. Zhao, Z. Yin, H. Cheng, T. Wu, “RankClus: Integrating Clustering with Ranking for Heterogeneous Information Network Analysis”, EDBT’09
- PathSim
    - Y. Sun, J. Han, X. Yan, P. S. Yu, and T. Wu, “PathSim: Meta Path-Based Top-K Similarity Search in Heterogeneous Information Networks”, VLDB’11

#### Candidate choices (Extreme, with at least 10 bonus point)

- Task-Guided and Path-Augmented Heterogeneous Network Embedding
    - T. Chen and Y. Sun, Task-guided and Path-augmented Heterogeneous Network Embedding for Author Identification, WSDM’17
    - You may need [TensorFlow](https://www.tensorflow.org/) or some other deep learning software to run SGD and optimize the embedding result `U`.
- Other papers listed in [this short summary](https://snowkylin.github.io/network-mining/heterogeneous-network/2017/04/25/heterogeneous-network-mining-index.html).

## Environments & Languages (updated)

- C++ (visual studio 2015 or gcc)
- Python (Anaconda 4.3.1, Python 2.7 version)
- MATLAB (MATLAB R2016b)
- **(updated)** PHP is allowed (the version will be 5.6.25). Any front end languages and libraries are acceptable, such as JavaScript, JQuery and D3.js. 
- **(updated)** Java is allowed (the version will be 1.8.0_121).
- **(updated)** If you really want to use Node.js, please give a good reason and detailed instruction about how to establish the environment to run your program, and then it can be allowed.

## Template of Report (LaTeX)

To be updated...

If you are new to LaTeX, it is suggested to read [LaTeX-cn](https://github.com/wklchris/Note-by-LaTeX/releases) written by Chris Wu, which is really concise and useful.

## Q&A

Feel free to ask any questions about this assignment by creating issues in this repository. I will reply as soon as possible. You can also email to [xihanli@pku.edu.cn](mailto:xihanli@pku.edu.cn).

