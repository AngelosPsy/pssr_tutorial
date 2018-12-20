---
title: "Tutorial for the pssr R package"
author: "Angelos-Miltiadis Krypotos & Gaetan Mertens"
output:
  pdf_document: default
  html_document: default
  md_document:
    variant: markdown_github
---

<style>
p.comment {
background-color: "white";
padding: 10px;
border: 1px solid black;
margin-left: 25px;
border-radius: 5px;
font-style: italic;
}

</style>



This document provides a brief tutorial for the [pssr](https://github.com/AngelosPsy/pssr) R package. Specifically, we first provide instructions on how to (install the package)[#installation]. Then, we explain each tab of the package (one by one)[#initiat]. Lastly, we go through a [hypothetical example](#hexample). 

Our R package provides a suite of functions for preregistrating and sharing data/materials. Although it was initially designed as an easy-to-use tool for experimental psychopathologists and other researchers in clinical psychology, it can be used from any researcher running experimental studies. The rationale behind the design of the package can be found in the pre-print [A Step-By-Step Guide on Preregistration and Effective Data Sharing for Psychopathology Research](https://osf.io/yvnfj/). Now, we move on to the main part of the tutorial.

## Installation instructions {#installation}
Before installing the software, make sure that you have the most recent versions of the following software installed: [R](https://cran.r-project.org), [Rtools](https://cran.r-project.org/bin/windows/Rtools/), and [git](https://git-scm.com/]), [pandoc](https://github.com/jgm/pandoc). You can also choose between installing [MikTex](https://miktex.org/download) or [tinytex](https://yihui.name/tinytex/).

After that, start a new R session and paste the following commands in the R console.


```r
if(!require(devtools)) { install.packages("devtools") } # Install devtools (in case you need to)
devtools::install_github("AngelosPsy/pssr")
```
If everything went as planned, the software is now ready to be used.

## Initiating a pssr session {#initiat}
The main function is the  pssr::shiny_app() which initiates a new [shiny](https://shiny.rstudio.com/) session. As in any other function in R, just paste


```r
pssr::shiny_app()
```

in the R console. After doing that, a new window will appear. We now explain each tab of the software.

## Create project Tab
For creating a new project, navigate to the 'Create project'. Then, place a name in the 'Project name' box and click on the 'Create new project'. In case you want to reopen an existing project, the user can just click on the 'Find existing project' box and navigate to an existing project. In case a folder is selected that was not created by the $pssr$, the program returns a warning. 

When a project folder is created, the program automatically creates a directory with the project's name. Inside the directory the following subdirectories are created: "analyses", "data", "manuscript", "material", and "preregistration". 

<img src="figures/cp.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" width="80%" />

## Preregistration Tab
For creating a preregistration document, you can enter a name in the "Enter name of the preregistration". Then, choose template you want to use so as
to form your preregistration. The pssr software supports 3 templates. These are the 'pss', the 'aspredicted' from the [aspredicted](aspredicted.org) website,
and the 'osf' from the (osf)[osf.io] website. In case the 'pss' template is selected, then a new tab is presented, with each tab now having different boxes
for every different piece of information that needs to be preregistrated (e.g., methods, statistical analyses). We describe more about this type of information
in our paper.

In case the 'aspredicted' or the 'osf' template are selected, then a new window will appear. The user then can use manipulate the text using the (Rmarkdown)[https://rmarkdown.rstudio.com] template. For these templates, we use the (prereg)[https://cran.r-project.org/web/packages/prereg/index.html] package
authored by (Frederik Aust)[https://github.com/crsh]. 

### Generate a pdf of the pregistration file
Under 'Preregistration' press 'Choose files'. On the pop up window, go to the 'preregistration' folder. Inside that folder, select the
'.Rmd' file with the name of the preregistration file you want to manipulate and click on 'Select'. After that, click on the 'Create PDF's'.
Then the pdf files of the preregistration files are now being saved in the 'preregistration' folder.

<img src="figures/p.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" width="80%" />

## Anonymize data
Our software can also be used to anonymize data. For that, navigate to the 'Anonymize data' folder. Then, choose a CSV file that can be used for
anonymizing data. The software currently accepts only csv files. After that, select the columns that will be anonymized. After selecting the columns,
you can select either to fill in the columns using random numbers or just encryption algorithms by clicking one of the options in the drop down menu named
'How to anonymize data?'.

<img src="figures/ad.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" width="80%" />

## Zip and encrypt data
The full project can be zipped and encrypted so that it can be easily shared with the rest of the community. For that, navigate to the 'Zip and encrypt data'
tab. Then, enter the password you want, select the columns that you want to zip and encrypt, and then click on the 'Encrypt Project files'.

<img src="figures/ed.png" title="plot of chunk unnamed-chunk-6" alt="plot of chunk unnamed-chunk-6" width="80%" />

# Hypothetical example {#hexample}

For this example, we are going to be based on the preregistration of the study ("Modality-specific dual-task interference on aversive memories")[https://osf.io/zgw3r/], written by Gaëtan Mertens, Vera Bouwman, Jonas Asmervik, & Iris M. Engelhard. Please note that we describe below more steps than the ones used in the preregistration.

# Step one: Initialise a project
First, we start by initializing a project by using the command `{r  eval = FALSE} pssr::shiny_app()`. If everything worked as planned, a new project is initialized.

# Step two: Fill in the details in the 'Create Project' tab {#step2}

Here, we first fill in the name of our project (i.e., Modality-specific dual-task interference on aversive memories). Then, we click on the _Create new project_ tab. On the window that appears, you can select the directory (i.e., computer folder) where you want your project folders to be stored. If anything goes as planned, the directory that the project is stored will be written on screen. Please note that everytime you want to open the projet, you can just click on the "Find existsting project", locate the folder that contains your project (for the example that would be the folder named "Modality-specific dual-task interference on aversive memories") and open it. Please note that if a folder is selected that was not created by the pssr, a warning will be returned.

# Step three: Preregistration

Now that the project has been created (see (Step two)[#step2]), we are ready to create our preregistration document. For that, first click on the _preregistration_ tab. We first need to name our preregistration document. This could be something as simple as "preregistration". Then, we need to choose one of the available preregistration templates. The pssr provides 3 different preregistration templates: the pss, aspredicted, and cos templates. The last two templates were provided by the (prereg)[https://cran.r-project.org/web/packages/prereg/index.html] R package of (Frederik Aust)[https://github.com/crsh]. The first template was written by us and it is the template we describe in our relevant (paper)[https://osf.io/yvnfj/]. Here, we descibe only the pss template as for the other two, there other relevant resources (e.g., (https://osf.io/zab38/wiki/home/)[https://osf.io/zab38/wiki/home/]). 

In order to select the pssr template, the user can just select the template from the drop down menu named _choose a pre-registration template_. Then, click on the _+ Create_ button. After doing that, a new tab will be created, with separate boxes for each one of the fields that need to be filled in. Here, we provide within boxes the inforation we have provided.

## Title
<p class="comment">
Modality-specific dual-task interference on aversive memories
</p>

## Author list
<p class="comment">
Gaëtan Mertens, Vera Bouwman, Jonas Asmervik, & Iris M. Engelhard
</p>

## Affiliation list
<p class="comment">
Department of Clinical Psychology, Utrecht University
</p>

## Background of the study
Study questions
<p class="comment">
This study will investigate whether the reduction of self-reported vividness and emotionality of aversive memories in dual-task paradigms can be enhanced by using modality-specific interference. 
</p>

## Study hypotheses
<p class="comment">
A greater reduction in vividness and emotionality in visual memories is expected after a visuospatial taxation task compared to an auditory taxation task. In addition, a greater reduction in vividness and emotionality in auditory memories is expected after an auditory taxation task compared to a visuospatial taxation task.
</p>

## Methods
Stimuli
<p class="comment">
Three visual stimuli (IAPS pictures 9181, 3400, and 6350) and three auditory stimuli (IADS sounds 286, 275, and 279) are randomly assigned to the three tasks. 
</p>

## Questionnaires
<p class="comment">
No questionnaires are included in this study.
</p>

## Equipment
<p class="comment">
This study will be run on a standard laboratory PC. The experiment was programmed in Inquisit v4.0.
</p>

## Procedure

<p class="comment">
All participants will complete three tasks: (1) Control task: watching a white screen, (2) Visual task: detecting a target letter (e.g., p) between distractors (e.g., q) appearing alternatingly on the sides of the computer screen (Homer, Deeprose, & Andrade, 2016), (3) Auditory task: detecting a target letter (e.g., d) between distractors (e.g., e) presented by male and female voices on alternating sides of the headphone. During each of the tasks participants will have to recall their memory for either an emotional picture or sound (also on a within-subject basis).
</p>

## Protocol

<p class="comment">
Protocol - Experiment Modality specific interference <br> <br>
Version: June 2018 <br> <br>
Materials: <br>
-	Computer with Inquisit experiment <br>
-	Chair <br>
-	Headphones <br>
-	2 pencils <br>
-	Protocol experimenter <br>
-	Counterbalance scheme <br>
-	Information letter <br>
-	Informed consent (2x) <br>
-	Questionnaire prior knowledge modality specificity <br>
-	Debriefing <br>
-	Money <br>
-	Money/course credits received checklist <br>
Preparation: <br>
  - Turn on the computer and log on -> right icon, password = fswlab <br>
  - Make sure that the sound on the computer is set correctly -> full? <br>
  - Open the experiment in Inquisit -> Labshare(L-schijf) -> Gaetan Mertens -> Experiment Modality specific <br> interference (Jonas Asmervik) FINAL -> Experiment.iqx <br>
  - Insert the correct participant and group number based on the counterbalance scheme <br>
Put on the red light in the cubicle when you enter the lab with the participant. <br> <br>
Introduction: <br> <br>
"Welcome to the eye-movement study with aversive images and sounds. I would like to ask you to switch off / silence your phone.  <br>
This study consists of a computer task which will take approximately 40 minutes. I would like you to read the information letter concerning this experiment. If you then decide to participate, I would like you to ask to fill in the informed consent." <br> <br>
Give participant the information letter. <br> <br>
When participant is done reading: <br>
"Do you have any questions? Would you like to participate?" <br> <br>
If yes, give two informed consents: <br>
"Please fill in these two forms. One is for you, the other is for our administration." <br> <br>
Instructions on computer task: <br>
"You now will start with the computer task. Please sit close to the desk with your upper body barely touching. <br>
During the experiment, sounds are presented to you through these headphones. Please wear the headphones throughout the experiment. <br> <br>
All instructions will appear on the screen. When you are finished, please come out and see me at the front desk. <br> <br>
Do you have any questions?" <br>
Answer any questions  <br> <br>
"You can press the spacebar when I have left the cubicle to start the experiment. Good luck." <br>
Leave the cubicle <br> <br>
End of the experiment: <br> <br>
When the participant is finished with the computer task, assess the prior knowledge of modality specificity questionnaire. <br> <br>
Provide debriefing and sign it after the participant has signed it. <br> <br>
Provide incentive: <br>
"This is the end of the experiment. Thank you for participating. You will receive 8 euro's / 1 course credit as incentive. Will you fill in this list?" <br>  <br>
</p>
### Statistical analyses

## Participant number
<p class="comment">
The sample size calculation is based on pilot data. As G-power does not allow for a repeated measures ANOVA within-within interaction, we calculated the sample size by using the dependent means t-test option. Therefore, we restructured the pilot data into two variables: congruent modality (M  reduction vividness = 21.53, SD = 19.99) and incongruent modality (M reduction vividness = 14.99, SD = 14.02) and determined the effect size (dz = 0.31). Sample size calculation using a dependent $t$-test with an a of .05 and statistical power of  1 - $\beta$ =  .80 indicated a required sample of 66 participants. Because of the counterbalance procedure (the sample size needs to be multipliable by 12) and feasibility, the final sample size will be 60 participants. Post hoc power calculations indicates that a power of .77 will be obtained with 60 participants, which we considered sufficient.
</p>

## Stopping rule
<p class="comment">
Data collection will continue until valid data for 60 participants is obtained.
</p>

## Confirm hypotheses
<p class="comment">
The memory vividness and emotionality scores will be analyzed separately in two repeated measures ANOVAs with task (visual, auditory, control) and stimuli (visual, auditory) as a within-subject factors and the difference scores (pre- and post-measurements) as dependent variable. To further explore the results, paired sample t-test will be performed to compare the different tasks per stimuli. The analyses will be conducted within the traditional null hypothesis testing framework (NHST) using an ??  of .05. <br> <br>
Our primary hypothesis is that there will be an interaction between task and stimuli, with greater memory vividness and emotionality difference scores in the visual task using a visual stimuli and greater memory vividness and emotionality difference scores in the auditory task using a auditory stimuli. In comparison, incongruent modality interferences are expected to show less reduction in memory vividness and emotionality. Furthermore, we expect overall greater reductions in memory vividness and emotionality in the experimental conditions compared to the control condition. 
</p>

## Disconfirm hypotheses
<p class="comment">
Any evidence opposite to the previous predictions would be provide first evidence of disconformination of our hypotheses.
</p>

## Other
<p class="comment">
Not applicable.
</p>

## References
<p class="comment">
Baddeley, A. D. (1983). Working Memory. Philosophical Transactions of the Royal Society of London. Series B, Biological Sciences, 302, 311-324. https://doi.org/10.1098/rstb.1983.0057
Homer, S. R., Deeprose, C., & Andrade, J. (2016). Negative mental imagery in public speaking anxiety: Forming cognitive resistance by taxing visuospatial working memory. Journal of Behavior Therapy and Experimental Psychiatry, 50, 77-82. https://doi.org/10.1016/j.jbtep.2015.05.004,
</p>

# Step four: Anonymize data
The anonymize data tab can be used for anonymizing the data easily. Please note, though, that all functions are provided as an easy step ensuring anonymization of the data. However, all users should check whether indeed the data are fully anonymized before releasing them in public. For the sake of the example, we will open the "exampleDataSet.csv". These data are already anonymized but we have added an extra column with random age numbers.  The data set looks as follows:


```
##    ID Auditory  Control     Vis1     Vis2     Vis3 Grand.Total Age
## 1   1 500.9775 348.7957 570.1647 614.3012 527.0000    508.7945  18
## 2   2 421.9895 418.1443 558.1918 557.9552 566.3333    491.1594  18
## 3   3 444.0851 419.3152 485.2432 482.8611 521.7200    466.2955  22
## 4   5 393.4330 346.9500 531.5208 566.7143 478.6795    437.0137  20
## 5   7 365.0928 315.7864 578.3571 455.0115 492.4725    434.8983  19
## 6   8 564.9041 382.7957 508.5493 522.3538 499.0896    488.7182  23
## 7   9 495.4568 358.5684 634.8194 634.6207 636.6000    539.1867  19
## 8  10 368.1020 374.3113 528.4412 522.1220 541.2000    433.7961  19
## 9  12 596.4444 510.3267 649.7143 578.2292 630.8333    579.9603  19
## 10 14 485.5238 349.2404 536.4127 502.9747 483.8485    461.0303  19
## 11 15 529.7447 377.1613 465.9091 655.6667 477.0294    483.7621  21
## 12 16 490.8571 492.7681 604.1765 643.5926 604.9032    557.2000  20
## 13 17 494.3810 392.1343 554.0488 473.1739 570.5588    484.2851  21
## 14 18 453.4533 363.6795 579.2381 535.0938 511.8980    480.8419  18
## 15 19 579.5455 361.6324 571.3750 600.2000 532.0462    512.3594  22
## 16 21 407.8861 354.6117 393.1316 425.8378 568.2000    419.6275  21
## 17 23 446.6429 349.3966 413.4426 354.0588 462.8462    406.1927  20
## 18 24 483.8219 400.9070 519.3611 407.5541 520.2899    471.3323  20
```

For our example, we would want to remove the age column as, for an unknown reason, we are afraid could detect some of our participants back based on their age -- a bit unrealistic argument in the present case but we just use this column for example purposes. In order to fill in this column with random numbers, we will follow the steps mentioned in _Anonymize data_ section. Specifically, by using the _Anonymize data_ tab, we will click on the _browse_ button, and select the  CSV file with our data (here _exampleDataSet.csv_). If everything went fine, then we should be able to see the first 2 columns of the data in our browswer. Then, in the _Select Columns_ box, we can select the columns that we want to be filled in with random numbers (here the _age_ column). In the _How to anonymize data?_ box, there are different options for anonymizng the data. Here, we stick to the random option (the default). After we do that, the "Anonymized data" section should now show the first 5 lines of our data. Importantly, the columns that we have selectedto be anonyzimed have changed both in name (i.e., the original column name + the suffix "_anonym"), Lastly, in case we want the anonymized data to be saved in our working directory, we need to go under the _Do you want the data to be saved_ radio button and click on 'Yes' (in the example it was set to 'No').

<img src="figures/anExample1.png" title="plot of chunk unnamed-chunk-8" alt="plot of chunk unnamed-chunk-8" width="80%" />

<img src="figures/anExample2.png" title="plot of chunk unnamed-chunk-9" alt="plot of chunk unnamed-chunk-9" width="80%" />

# Step five: Zip and encypt data
Here, we just type in a password in the _Enter password_ field (here the word 'password'). Then, we select the subfolders that we want to be encrypted (here the 'Analyses' and 'Material' subfolders). Lastly, we click on the _Encrypt Project files_ button. If anything went as predicted, the directory where the zip file was located should be shown on screen (here hidden for privacy issues).

<img src="figures/encryptExample.png" title="plot of chunk unnamed-chunk-10" alt="plot of chunk unnamed-chunk-10" width="80%" />

# Step six: Record changes
Although this is descibed as the sixth step, the tab named "Record changes" should be visited often during the whole project. Specifically, it is best to record as many changes as possible as this will provide a better view of the changes made throughout the whole project. In our example, we have just filled in a username and an email. Then, and every time we want to timestamp the changes made in the project, we just provide a brief description of the changes we have made (e.g., anonymized data) and then click on the 'timestamp changes'. Whenever we want to see if any changes have been made in the files, we can click on the 'track changes' button. 

As explained in our main paper, no new copies of the files are made. However, sometimes maybe the user wants to revert to an older version of the files. The _version control_ tab was designed for exactly this. For that, just click on the folders you want to revert to and then go to the commit you want to revert to using the _Go to Commit_ button. Please note that there should be at least one commit in order for this future to work. In case of no commits, the tab will return an error.
