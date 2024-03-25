# HOME
## Introduction

###  What it is 

The fast development of statistical methods and machine learning algorithms applied to data from cyberinfrastructures offers genuine opportunities to reveal solid Earth's secular evolution and chemistry. However, in their present state, cyberinfrastructures are composed of raw high temperature geochemical data with missing categories, a non-negligible proportion of errors, including age information, and misplaced chemical compositions that may be inconsistent with publications. These unintended errors are mainly caused by (1) errors in manual data entry; (2) the lack of standards to publish high temperature geochemistry data, and the limitations of the optical character recognition techniques used to convert tabular data into readable documents. Furthermore, there is a lack of inherent relationships between rocks and minerals.

With joint efforts of 20 geochemists, we have constructed a benchmark dataset in high temperature geochemistry. Up to now, 200,000 rock and mineral data have been checked and corrected manually based on the FAIR principle (findable, accessible, interoperable, and reusable). Furthermore, the database provides raw data downloaded from cyberinfrastructures and their corresponding data after data cleaning, which can be used to check the effectiveness of data filtering algorithms. Therefore, the 200,000 rock and mineral data include (1) raw-clean data pairs; (2) mineral-mineral and mineral-rock relations. The database system is developed using Postgre SQL and Java, utilizing the VUE and SpringBoot frameworks for the front and back ends. The web portal offers a querying function to search for specific geochemistry data and a matching function to find rock-mineral combinations and mineral-mineral pairs generated under the same formation conditions. In the future, the database will be uploaded to the Deep-time Digital Earth program platform for data integration.



### Key features

1. FAIR principle (Findable, Accessible, Interoperable, Reusable).

2. Manual cleaning ~ 200,000 rock and mineral data.
3. Raw-clean data pairs to test data filtering algorithms.
4. User-friendly Website: https://htgdb.deep-time.org



### Some figures

- Website Display

![首页图片][(https://github.com/Christine1230/test1/docs/source/首页图片.png)](https://github.com/Christine1230/test1/blob/5fd0926f82321da5772294e4f5197b91f848bce1/docs/source/%E9%A6%96%E9%A1%B5%E5%9B%BE%E7%89%87.png)

- The Point of Website

![网站指南用途](docs/source/image/网站指南用途.png)

### Related report

1. Yang Lyu, J ZhangZhou, ZJU Earth Data Team. Bringing Data Clarify from Cyberinfrastructures: A Benchmark Database in High Temperature Geochemistry. Americal Geophysical Union Fall Meeting (AGU), 2023, San Francisco, United States. (Poster, in Person)

2. Yang Lyu, J ZhangZhou. High temperature Geochemistry Database - high quality segmented domain database.Annual Meeting of Chinese Geoscience Union (CGU), 2023, Zhuhai, China. (Oral Presentation, in Chinese)
3. Yang Lyu, J ZhangZhou. High temperature Geochemistry Database - high quality segmented domain database. The 7th Conference on Earth System Science (CESS), 2023, Shanghai, China. (Oral Presentation, in Chinese)



## Team

### Team Info

**Team Leader:** 

Yang Lyu

**Technical Guidance:** 

- Shengfeng Pan
- Jinyuan Zhang

**Data Arrangement:** 

- ZJU Earth Data Team,

- Siqi Huang 

**UI / Front-end:** 

- Shuyi Li

- Yutong Sun

**Back-end:**

-  Junbo Wang
-  Jianing Wang
-  Ruitao Chang

**User Docs:**

-  Nuoer Li

### Join Us

If you join the HTG team, you will get:

1. Participate in development process and internal testing of the database.
2. Give priority to using data and algorithms in the database.
3. Have access to the latest updates to database.

**Please send the email to join us: lyuyang1007@zju.edu.cn**



## Change Log

| Fhase | Change Time |                           Content                            |
| :---: | :---------: | :----------------------------------------------------------: |
| V1.0  |   2023.12   | near 200,000 samples (rock, mineral, inclusion, experiment sample) |
| V2.0  | wait for it |                     expected at 2024.03                      |
