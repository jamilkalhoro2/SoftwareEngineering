# SoftwareEngineering
1st Paper

Title And Authors:-  

An Empirical Study of Build Failures in the Docker Context 

Yiwen Wu 

Yang Zhang 

Tao Wang 

Huaimin Wang 

Conference Program ICSE 2020 

Introduction And Motivation:-  

Docker is one of the most popular containerization tools in current DevOps practice. It enables the encapsulation of software packages into containers and can run on any system . Since inception in 2013, Docker containers have been downloaded 130B+ times1 . The “Annual Container Adoption” report2 found that 79% of companies chose Docker as their primary container technology. With the widespread use and influence of Docker, many studies have been recently conducted to investigate its ecosystem configuration file. Those works have emerged a lot of great findings and brought many practical implications to developers, but were not designed to look into the details of Docker builds. Building is crucial to the software development process, which automates the process by which sources are compiled, linked, tested, packaged, and transformed into executable units. 

Research And Methodology:-  

• RQ1: (Frequency) How often do Docker builds fail? 

• RQ2: (Fix effort) How long does it take to fix Docker build failures? 

• RQ3: (Evolution) How do failures frequency and fix effort evolve across time? 

The rest of this paper is organized as follows: Section 2 describes the study setup. Section 3 presents our study results. Section 4 outlines the research agenda and Section 5 discusses the threats to validity. Finally, Section 6 concludes the paper.  

Motivation. The initial RQ aims at understanding how often Docker builds fail. Previous studies found a median of 37.4% of C++ builds and a 29.7% of Java builds at Google to be failing [7], and a 13.2% in the Visual Studio Context [5]. However, even though Docker is widely used in the open-source community [3], little research has been conducted on the Docker build failures. Thus, investigating the frequency of broken builds will help us to characterize the significance of build failures in the Docker context, and motivate the importance of our study. This RQ2 aims at understanding the time spent by developers fixing the Docker build failures. In the context of Google, developers spend a median of 5 and 12 minutes fixing C++ and Java build failures, respectively. This RQ aims at understanding whether the ratio (fix time) of broken builds is a constant value or fluctuates across time. Prior works [5, 7, 11] mainly focus on the static analysis of build failures, few studies have investigated the evolution of build failures, the only exception being the study by Zolfagharinia et al. 

Result:- RQ1: Frequency analysis:-  

In the Docker context, 152,897 of the 857,086 (17.8%) studied Docker builds fail, which is above the 11% as reported by Zhang et al. [11] (in the CI builds context) but below the 28.5% as reported by Seo et al. [7] (in the Java builds context). As discussed in the previous study [5], build failure rates are highly sensitive to changes in context. Further, we find that 3,260 (85.2%) projects have at least one broken build; 389 (10.2%) projects have at least 50% of broken builds. Thus, build failures are very common in the Docker context, and affect most of the open-source projects. 

RQ2: Fix effort analysis:- 

s the distribution of resolution time of broken Docker builds. Of the 10,566 valid Fail-Fix pairs, 511 (4.8%) pairs take less than 1 minute to fix; 2,105 (19.9%) pairs take 1 to 10 minutes to fix; 4,511 (42.7%) pairs take 10 to 100 minutes to fix; and 3,431 (32.5%) pairs take more than 100 minutes to fix. On average, broken builds in our dataset take an average of 124.5 minutes to fix (median time: 44.2 minutes), which is much longer than in Google’s study (less than 12 minutes) [7]. Many factors may contribute to this difference, e.g., work environments and tooling. Also, this large difference may be due to Google requiring developers to respond quickly to failures to avoid affecting a wide range of developers.  

RQ3: Evolution analysis:- 

w the distribution of failure ratio and fix time in different time periods, respectively. The red regression line shows the corresponding evolutionary trend over the eleven studied time periods (from 2014a to 2019a). We find that, the median build failure ratio decreases from 28.6% in 2014a to 15.8% in 2014b. While the median ratio increases across time from 16.7% in 2015a to 36.9% in 2019a. As for the fix time, the median build fix time decreases across time from 64 minutes in 2014a to 19 minutes in 2015a. While the median fix time increases across time from 22 minutes in 2015b to 97 minutes in 2019a. However, as the regression lines show, the overall build failure ratio and fix time have slightly increasing trends, especially when considering the logarithmic y-scale. These findings are very different from Zolfagharinia et al. [14], thus verifying that build failure rates and fix time are highly dependent on the study context. 

Conclusion:- Executing the build process (i.e., building) is crucial to the software development process. Many prior studies have been published describing build failures in different contexts, to the best of our knowledge, this study is the first to conduct a large-scale empirical study of build failures in the Docker context. We quantify and analyze Docker build failures, including frequency, fix effort, and their evolution based on 857,086 Docker builds from 3,828 GitHub open-source projects. Our findings motivate the need for collecting more empirical evidence to better understand how developers build Docker containers and to guide future process refinements and tool development to improve Docker building efficiency. 
