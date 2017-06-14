# Assignment of course "Data Warehousing and Data Mining Technology", Spring and Summer Semester, 2017.

This is a more detailed instruction about the assignment of DW & DM course.

**NOTICE: The final exam will be held on 8:30 - 10:30 am, June 15th in Classroom 307, Science Teaching Building. The assignment should be handed in before 23:59, June 15th.**

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
    - <font color="red">**(updated)**</font> Your application should be able to import the .csv data to MySQL server (without help of management software such as PHPMyAdmin) and load data from it.
    - <font color="red">**(updated)**</font> You can assume that there is an empty database named "bank" with username "test" and empty password in the local MySQL database. This account have all privilege to manipulate the "bank" database.
- Showing 1~9 distribution of attributes at the same time.
    - Users are able to select which attribute(s) to show.
    - However, you need to import **all the data** to MySQL server, not 9 columns of them!
- <font color="red">**(updated)**</font> Interactive UI
    - Users without much programming knowledge can operate your application by select, click and other simple actions.
    - Web or desktop based UI is OK. Command-line interface is not acceptable.
- <font color="blue">**(bonus point)**</font> You will get more score if your application can support more OLAP operations, such as roll-up and drill-down.
- <font color="blue">**(bonus point)**</font> You will get more score if your application can handle time and date. (you need to provide some other time-related data to test this feature)

#### Suggestions <font color="red">(new)</font>

- You may use Python (with matplotlib, mysqldb and so on) or PHP to build the application.
- If you choose PHP, [D3.js](https://d3js.org/), a really powerful tool for interactive data visualization, is recommmended as the front-end library.

### Project 2: Visualization of data correlation

The dataset and requirements are the same with project 1, but the task is to show the correlation of two selected attributes.

### Project 3: "Phrase" mining based on frequent patterns

- Dataset: 
    - [Gutenberg dataset](https://web.eecs.umich.edu/~lahiri/gutenberg_dataset.html) (in FTP server)
    - [Amazon review data](http://jmcauley.ucsd.edu/data/amazon/) (optional)
    - [DBLP](http://dblp.uni-trier.de/faq/How+can+I+download+the+whole+dblp+dataset) (title) (optional)
    - [ACL](http://clair.eecs.umich.edu/aan/index.php) (title & abstract) (optional)
- Your task: design and implement a data mining algorithm to find the "phrase" in these texts based on frequent patterns.
- <font color="red">**(updated)**</font> The "phrase" here can be more general. Here, two words can be called "phrase" when they always appear together in one sentence, even if they are not adjacent (maybe this will be easier for you). Sorry for this ambiguous point and thank @WillsNew. However, it has more actual meaning when we only consider words that are adjacent. That needs some additional techniques and it is put in the "bonus point" part.

#### Suggestions <font color="red">(new)</font>

- The dataset is quite large. You may select **part of them** that you are interested in. For example, all books written by Charles Dickens, all fairy tale books or all books that is written in 18th century. For amazon review data, you can just select the type of reviews that you are interested in.
- <font color="blue">**(bonus point)**</font> You will get more score by applying your algorithm to other dataset (such as Amazon review data, DBLP titles and so on).
- <font color="blue">**(bonus point)**</font> You may want to do some "real phrase mining", i.e., finding phrases like "support vector machines", "reinforcement learning" and so on. That needs some additional techniques and you can find some of them in [this slide](http://hanj.cs.illinois.edu/cs512/slides/3-Textmining_Part1.pptx), such as KERT (page 19-21) and ToPMine (page 24-36). It is encourged to try these frequent-pattern-mining based methods (or design your own method) to improve your result. 
- <font color="blue">**(bonus point)**</font> You can see sentences as "baskets" as the slide says. However, I suggest you to try some different ways, such as:
    - See paragraphs as baskets
    - See chapters as baskets
    - See books as baskets (this might be harder)
    - (For amazon review data) See reviews as baskets
- You may apply some "stop word" methods, which is common in NLP related tasks.
- You may use [Expat](https://docs.python.org/2/library/pyexpat.html) to read data from xml file (such as DBLP). It is a quite useful skill.
- You may use Python for data preprocessing. However, if you want to make you program more efficient, you may use c++ to implement the core algorithm.

### Project 4: Implementation of a "influential" data mining algorithm

- Your task: just as the title says.
- Prepare the dataset by yourself.
- Don't implement your algorighm by a single line with the help of library function, such as:
    - res = xxxlib.Apriori(data)
    - rank = xxxlib.PageRank(data)
- If you want to implement other algorithms, please post an issue in this repo.
- For the hard and extreme level, there is [a short summary](https://snowkylin.github.io/network-mining/heterogeneous-network/2017/04/25/heterogeneous-network-mining-index.html) of them. If you want to implement one of them, you are warmly welcomed to communicate with me (the teaching assistant) after reading the corresponding paper. Maybe I will give you some specific help depending on which paper you select.
- <font color="red">**(updated)**</font> For the hard and extreme level, there are two slides that may help you: [Mining heterogeneous information networks](http://hanj.cs.illinois.edu/cs512/slides/2-Mining_Network.pptx), [Mining heterogeneous information networks: Part2](http://hanj.cs.illinois.edu/cs512/slides/2-Mining_Network_Part2.pptx).

#### Candidate choices (Normal)

- FP algorithm
    - <font color="red">**(updated)**</font> The gloceries dataset (in FTP server, or you can use dataset larger than this)
- PageRank
    - at least 10000 nodes and 100000 edges.

#### Candidate choices (Hard, with at least 5 <font color="blue">**bonus point**</font>)

- <font color="red">**(updated)**</font> RankClus
    - Y. Sun, J. Han, P. Zhao, Z. Yin, H. Cheng, T. Wu, “RankClus: Integrating Clustering with Ranking for Heterogeneous Information Network Analysis”, EDBT’09
- <font color="red">**(updated)**</font> PathSim
    - Y. Sun, J. Han, X. Yan, P. S. Yu, and T. Wu, “PathSim: Meta Path-Based Top-K Similarity Search in Heterogeneous Information Networks”, VLDB’11

#### Candidate choices (Extreme, with at least 10 <font color="blue">**bonus point**</font>)

- <font color="red">**(updated)**</font> Task-Guided and Path-Augmented Heterogeneous Network Embedding
    - T. Chen and Y. Sun, Task-guided and Path-augmented Heterogeneous Network Embedding for Author Identification, WSDM’17
    - You may need [TensorFlow](https://www.tensorflow.org/) or some other deep learning software to run SGD and optimize the embedding result `U`.
- <font color="red">**(updated)**</font> Other papers listed in [this short summary](https://snowkylin.github.io/network-mining/heterogeneous-network/2017/04/25/heterogeneous-network-mining-index.html).

## Environments & Languages (updated)

- C++ (visual studio 2015 or gcc)
- Python (Anaconda 4.3.1, Python 2.7 version)
- MATLAB (MATLAB R2016b)
- <font color="red">**(updated)**</font> PHP is allowed (the version will be 5.6.25). Any front end languages and libraries are acceptable, such as JavaScript, JQuery and D3.js. 
- <font color="red">**(updated)**</font> Java is allowed (the version will be 1.8.0_121).
- <font color="red">**(updated)**</font> If you really want to use Node.js, please give a good reason and detailed instruction about how to establish the environment to run your program, and then it can be allowed.

## Template of Report (LaTeX)

Please check the `report` folder in this repo to get the LaTeX template of report. It is suggested to use [TeXLive 2016](http://tug.org/texlive) (download ISO [here](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/), Internet installation is quite slow) and [TeXStudio](http://texstudio.sourceforge.net/). You may use XeLaTeX to compile the .tex file.

If you are new to LaTeX, it is suggested to read [LaTeX-cn](https://github.com/wklchris/Note-by-LaTeX/releases) written by Chris Wu, which is really concise and useful.

For others who do not use LaTeX, you can write your report according to the format shown in `report\report.pdf`.

## Q&A

Feel free to ask any questions about this assignment by creating issues in this repository. I will reply as soon as possible. You can also email to [xihanli@pku.edu.cn](mailto:xihanli@pku.edu.cn).

