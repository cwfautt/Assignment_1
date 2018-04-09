Assignment 1
==============

# Template for Unix, git, and Sequence Alignment Assignments (20 pts possible)

__Full Name:__ Chad Fautt

__Student ID:__ 912741143

*_Any code should be formatted as such_*

## Markdown

Name: Eunice Chan
Major: **Genetics**
Year: _Senior_

| School | Year | Location |
|:------:|:----:|:--------:|
| Saint Stevens College | 2008 - 2014 | Hong Kong|
| UC Davis | 2014 - present | Davis

##### Likes:
* [Going to the movies](www.moviepass.com)
* Listening to music
* Pizza (eating it?)


## Unix

Paste the `date` command that you used for exercise one here:

    date "+%Y-%m-%d %H:%M:%S"

## Git

Paste the URL for the shared github repository that you created with your lab partners here.  Use proper markdown formatting: [Lab2](https://github.com/geebus77/lab2)




## Sequence Alignment

*_Please answer the following questions Be clear and concise with any written answers._*

** Unless otherwise noted we are not requiring you to include your code here.  However, I advise that you record it in a separate Markdown file for your reference.  That way if you need it again (e.g. for the midterm) you have a record of what you did**

__1.__ Paste in the result of the `ls -lR Data` command.

    Data:
    total 8
    drwxrwxr-x 4 ubuntu ubuntu 4096 Apr  5 15:42 Sequences/
    drwxrwxr-x 5 ubuntu ubuntu 4096 Apr  5 15:45 Species/

    Data/Sequences:
    total 8
    drwxrwxr-x 2 ubuntu ubuntu 4096 Apr  5 16:02 Genome/
    drwxrwxr-x 2 ubuntu ubuntu 4096 Apr  5 16:00 Proteome/

    Data/Sequences/Genome:
    total 286480
    -rw-rw-r-- 1 ubuntu ubuntu 121183082 Apr  5 15:31 A.thaliana.fa
    -rw-r--r-- 1 ubuntu ubuntu     53248 Apr  5 15:53 C.elegans.fa
    -rw-r--r-- 1 ubuntu ubuntu 172113892 Apr  5 15:59 D.melanogaster.fa

    Data/Sequences/Proteome:
    total 66228
    -rw-r--r-- 1 ubuntu ubuntu 20006289 Mar 28  2015 A.thaliana.fa
    -rw-r--r-- 1 ubuntu ubuntu 14931762 Apr  5 15:55 C.elegans.fa
    -rw-r--r-- 1 ubuntu ubuntu 32872415 Apr  5 16:00 D.melanogaster.fa

    Data/Species:
    total 12
    drwxrwxr-x 2 ubuntu ubuntu 4096 Apr  5 16:16 A.thaliana/
    drwxrwxr-x 2 ubuntu ubuntu 4096 Apr  5 16:16 C.elegans/
    drwxrwxr-x 2 ubuntu ubuntu 4096 Apr  5 16:16 D.melanogaster/

    Data/Species/A.thaliana:
    total 0
    lrwxrwxrwx 1 ubuntu ubuntu 13 Apr  5 16:11 GENOME.fa -> A.thaliana.fa
    lrwxrwxrwx 1 ubuntu ubuntu 13 Apr  5 16:15 PROTEIN.fa -> A.thaliana.fa

    Data/Species/C.elegans:
    total 0
    lrwxrwxrwx 1 ubuntu ubuntu 12 Apr  5 16:13 GENOME.fa -> C.elegans.fa
    lrwxrwxrwx 1 ubuntu ubuntu 12 Apr  5 16:15 PROTEIN.fa -> C.elegans.fa

    Data/Species/D.melanogaster:
    total 0
    lrwxrwxrwx 1 ubuntu ubuntu 17 Apr  5 16:14 GENOME.fa -> D.melanogaster.fa
    lrwxrwxrwx 1 ubuntu ubuntu 17 Apr  5 16:15 PROTEIN.fa -> D.melanogaster.fa


__2.__ Paste in the markdown table from the lab manual that includes for each genome:

|     | A.thaliana | C.elegans | D.melanogaster |  
|:----:|:----------:|:---------:|:--------------:|
|**file size (bytes)**|121,183,082|   53,248 **(??)**  | 172,113,892   |  
|**# of chromosomes**| 7 | 1 **(??)** | 15 |  
|  **genome size (bp)**  | 121,182,535 |53246 **(??)**  |172,111,277 |  
| **# of protein-coding genes** |35,386| 26,757 | 30,307 |   
| **average protein length (AA)** | 414 |  453|  672|

For _ONE_ of the files, provide the code that you used to answer these questions:

* Size of the file:

      wc -c A.thaliana.fa

* Number of chromosomes:

      grep \n -c A.thaliana.fa

* Size of the genome in bp

      grep \n -v A.thaliana.fa | wc -c

* Number of protein-coding genes

      grep Symbols -c A.thaliana.fa

* Average protein length

      All_AA=$(grep -v Symbols A.thaliana.fa | wc -m)
      num_Prot=$(grep -c Symbols A.thaliana.fa)
      echo $((All_AA /num_Prot))


__3.__ How do you know that when you use `shuffleseq` that the sequences have the same exact composition?

__4.__ Create a text based "histogram" as described in the lab manual
that shows the distribution of scores when aligning shuffled sequences.

__5.__ Is the shape of the curve normal? Do you expect it to be normal?

__6.__ Do you expect all protein comparisons to have the same distribution?

__7.__ How would protein composition and length affect the scores?

__8.__ How would the scoring matrix and gap penalties affect the scores?

__9.__ How many amino acids can be aligned per second?  How many amino acids need to be aligned for the experiment?  How long would it take to compare the two proteomes?

__10.__ Starting with the C. elegans B0213.10 protein, find the best
match in the A. thaliana and D. melanogaster proteomes with `water`.
Record their alignment scores, percent identities, and protein names
here.  (Use a markdown table!)

__11.__ What is the expected (average) score of each pairwise alignment
at random? (Perform some shuffled alignments to get an idea of what the
random expectation is).

__12.__ How many Z-scores away from the mean is the best alignment?

__13.__ Briefly discuss the statistical and biological significance of your results.
