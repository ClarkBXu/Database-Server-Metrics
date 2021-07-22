# Database-Server-Metrics
Jupyter Notebook for Analyzing, Processing, and Clustering of Time Series for Database Server Metrics

## Author
Clark Xu - July 21, 2021

## Purpose
The notebook applies filters to achieve a dimensionality reduction of 544 to 77 features. It visualizes the resulting 77-dimensional space by feature distribution, correlation, coincidence, and term frequency. Next it presents a user-defined function for feature pre-processing and clustering of time series database metrics. Finally it clusters the filtered data into 3 time series groups and visualizes the resulting clusters for key metrics such as rollbacks vs commits, reads vs commits, cpu/disk/memory usage. Contribution to the MariaDB Foundation.

MariaDB documented at: https://mariadb.org/ <br>
Jupyter Notebook documented at: https://jupyter.org/

## Specifications and Dependencies
### Specifications:
Python 3
### Dependencies:
pandas, warnings, matplotlib, sklearn, seaborn, datetime, numpy, 

## Details
Notebook Data Source: <br>


Notebook Name: <br>
Database-Server-Metrics.ipynb

Notebook Output: <br>
41 Jupyter Notebook cells as described above

## Licensing (Creative Commons Attribution-NonCommercial-NoDerivatives)
4.0 International Public License <br>
Copyright 2021 Clark Xu

By exercising the Licensed Rights (defined below), You accept and agree to be bound by the terms and conditions of this Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International Public License ("Public License"). To the extent this Public License may be interpreted as a contract, You are granted the Licensed Rights in consideration of Your acceptance of these terms and conditions, and the Licensor grants You such rights in consideration of benefits the Licensor receives from making the Licensed Material available under these terms and conditions.

Section 1 – Definitions. <br>
a.	Adapted Material means material subject to Copyright and Similar Rights that is derived from or based upon the Licensed Material and in which the Licensed Material is translated, altered, arranged, transformed, or otherwise modified in a manner requiring permission under the Copyright and Similar Rights held by the Licensor. For purposes of this Public License, where the Licensed Material is a musical work, performance, or sound recording, Adapted Material is always produced where the Licensed Material is synched in timed relation with a moving image. <br>
b.	Copyright and Similar Rights means copyright and/or similar rights closely related to copyright including, without limitation, performance, broadcast, sound recording, and Sui Generis Database Rights, without regard to how the rights are labeled or categorized. For purposes of this Public License, the rights specified in Section 2(b)(1)-(2) are not Copyright and Similar Rights. <br>
c.	Effective Technological Measures means those measures that, in the absence of proper authority, may not be circumvented under laws fulfilling obligations under Article 11 of the WIPO Copyright Treaty adopted on December 20, 1996, and/or similar international agreements. <br>
d.	Exceptions and Limitations means fair use, fair dealing, and/or any other exception or limitation to Copyright and Similar Rights that applies to Your use of the Licensed Material. <br>
e.	Licensed Material means the artistic or literary work, database, or other material to which the Licensor applied this Public License. <br>
f.	Licensed Rights means the rights granted to You subject to the terms and conditions of this Public License, which are limited to all Copyright and Similar Rights that apply to Your use of the Licensed Material and that the Licensor has authority to license. <br>
g.	Licensor means the individual(s) or entity(ies) granting rights under this Public License. <br>
h.	NonCommercial means not primarily intended for or directed towards commercial advantage or monetary compensation. For purposes of this Public License, the exchange of the Licensed Material for other material subject to Copyright and Similar Rights by digital file-sharing or similar means is NonCommercial provided there is no payment of monetary compensation in connection with the exchange. <br>
i.	Share means to provide material to the public by any means or process that requires permission under the Licensed Rights, such as reproduction, public display, public performance, distribution, dissemination, communication, or importation, and to make material available to the public including in ways that members of the public may access the material from a place and at a time individually chosen by them. <br>
j.	Sui Generis Database Rights means rights other than copyright resulting from Directive 96/9/EC of the European Parliament and of the Council of 11 March 1996 on the legal protection of databases, as amended and/or succeeded, as well as other essentially equivalent rights anywhere in the world. <br>
k.	You means the individual or entity exercising the Licensed Rights under this Public License. Your has a corresponding meaning. <br>

Section 2 – Scope. <br>
a.	License grant.  <br>
1.	Subject to the terms and conditions of this Public License, the Licensor hereby grants You a worldwide, royalty-free, non-sublicensable, non-exclusive, irrevocable license to exercise the Licensed Rights in the Licensed Material to:  <br>
A.	reproduce and Share the Licensed Material, in whole or in part, for NonCommercial purposes only; and <br>
B.	produce and reproduce, but not Share, Adapted Material for NonCommercial purposes only. <br>
2.	Exceptions and Limitations. For the avoidance of doubt, where Exceptions and Limitations apply to Your use, this Public License does not apply, and You do not need to comply with its terms and conditions. <br>
3.	Term. The term of this Public License is specified in Section 6(a). <br>
4.	Media and formats; technical modifications allowed. The Licensor authorizes You to exercise the Licensed Rights in all media and formats whether now known or hereafter created, and to make technical modifications necessary to do so. The Licensor waives and/or agrees not to assert any right or authority to forbid You from making technical modifications necessary to exercise the Licensed Rights, including technical modifications necessary to circumvent Effective Technological Measures. For purposes of this Public License, simply making modifications authorized by this Section 2(a)(4) never produces Adapted Material. <br>
5.	Downstream recipients. <br>
A.	Offer from the Licensor – Licensed Material. Every recipient of the Licensed Material automatically receives an offer from the Licensor to exercise the Licensed Rights under the terms and conditions of this Public License. <br>
B.	No downstream restrictions. You may not offer or impose any additional or different terms or conditions on, or apply any Effective Technological Measures to, the Licensed Material if doing so restricts exercise of the Licensed Rights by any recipient of the Licensed Material. <br>
6.	No endorsement. Nothing in this Public License constitutes or may be construed as permission to assert or imply that You are, or that Your use of the Licensed Material is, connected with, or sponsored, endorsed, or granted official status by, the Licensor or others designated to receive attribution as provided in Section 3(a)(1)(A)(i). <br>
b.	Other rights. <br>
1.	Moral rights, such as the right of integrity, are not licensed under this Public License, nor are publicity, privacy, and/or other similar personality rights; however, to the extent possible, the Licensor waives and/or agrees not to assert any such rights held by the Licensor to the limited extent necessary to allow You to exercise the Licensed Rights, but not otherwise. <br>
2.	Patent and trademark rights are not licensed under this Public License. <br>
3.	To the extent possible, the Licensor waives any right to collect royalties from You for the exercise of the Licensed Rights, whether directly or through a collecting society under any voluntary or waivable statutory or compulsory licensing scheme. In all other cases the Licensor expressly reserves any right to collect such royalties, including when the Licensed Material is used other than for NonCommercial purposes. <br>

Section 3 – License Conditions. <br>
Your exercise of the Licensed Rights is expressly made subject to the following conditions. <br>
a.	Attribution. <br>
1.	If You Share the Licensed Material, You must: <br>
A.	retain the following if it is supplied by the Licensor with the Licensed Material: <br>
i.	identification of the creator(s) of the Licensed Material and any others designated to receive attribution, in any reasonable manner requested by the Licensor (including by pseudonym if designated); <br>
ii.	a copyright notice; <br>
iii.	a notice that refers to this Public License; <br>
iv.	a notice that refers to the disclaimer of warranties; <br>
v.	a URI or hyperlink to the Licensed Material to the extent reasonably practicable; <br>
B.	indicate if You modified the Licensed Material and retain an indication of any previous modifications; and <br>
C.	indicate the Licensed Material is licensed under this Public License, and include the text of, or the URI or hyperlink to, this Public License.
For the avoidance of doubt, You do not have permission under this Public License to Share Adapted Material. <br>
2.	You may satisfy the conditions in Section 3(a)(1) in any reasonable manner based on the medium, means, and context in which You Share the Licensed Material. For example, it may be reasonable to satisfy the conditions by providing a URI or hyperlink to a resource that includes the required information. <br>
3.	If requested by the Licensor, You must remove any of the information required by Section 3(a)(1)(A) to the extent reasonably practicable. <br>

Section 4 – Sui Generis Database Rights. <br>
Where the Licensed Rights include Sui Generis Database Rights that apply to Your use of the Licensed Material: <br>
a.	for the avoidance of doubt, Section 2(a)(1) grants You the right to extract, reuse, reproduce, and Share all or a substantial portion of the contents of the database for NonCommercial purposes only and provided You do not Share Adapted Material; <br>
b.	if You include all or a substantial portion of the database contents in a database in which You have Sui Generis Database Rights, then the database in which You have Sui Generis Database Rights (but not its individual contents) is Adapted Material; and <br>
c.	You must comply with the conditions in Section 3(a) if You Share all or a substantial portion of the contents of the database. <br>
For the avoidance of doubt, this Section 4 supplements and does not replace Your obligations under this Public License where the Licensed Rights include other Copyright and Similar Rights. <br>

Section 5 – Disclaimer of Warranties and Limitation of Liability. <br>
a.	Unless otherwise separately undertaken by the Licensor, to the extent possible, the Licensor offers the Licensed Material as-is and as-available, and makes no representations or warranties of any kind concerning the Licensed Material, whether express, implied, statutory, or other. This includes, without limitation, warranties of title, merchantability, fitness for a particular purpose, non-infringement, absence of latent or other defects, accuracy, or the presence or absence of errors, whether or not known or discoverable. Where disclaimers of warranties are not allowed in full or in part, this disclaimer may not apply to You. <br>
b.	To the extent possible, in no event will the Licensor be liable to You on any legal theory (including, without limitation, negligence) or otherwise for any direct, special, indirect, incidental, consequential, punitive, exemplary, or other losses, costs, expenses, or damages arising out of this Public License or use of the Licensed Material, even if the Licensor has been advised of the possibility of such losses, costs, expenses, or damages. Where a limitation of liability is not allowed in full or in part, this limitation may not apply to You. <br>
c.	The disclaimer of warranties and limitation of liability provided above shall be interpreted in a manner that, to the extent possible, most closely approximates an absolute disclaimer and waiver of all liability. <br>

Section 6 – Term and Termination. <br>
a.	This Public License applies for the term of the Copyright and Similar Rights licensed here. However, if You fail to comply with this Public License, then Your rights under this Public License terminate automatically. <br>
b.	Where Your right to use the Licensed Material has terminated under Section 6(a), it reinstates: <br>
1.	automatically as of the date the violation is cured, provided it is cured within 30 days of Your discovery of the violation; or <br>
2.	upon express reinstatement by the Licensor. <br>
For the avoidance of doubt, this Section 6(b) does not affect any right the Licensor may have to seek remedies for Your violations of this Public License.
c.	For the avoidance of doubt, the Licensor may also offer the Licensed Material under separate terms or conditions or stop distributing the Licensed Material at any time; however, doing so will not terminate this Public License. <br>
d.	Sections 1, 5, 6, 7, and 8 survive termination of this Public License. <br>

Section 7 – Other Terms and Conditions. <br>
a.	The Licensor shall not be bound by any additional or different terms or conditions communicated by You unless expressly agreed. <br>
b.	Any arrangements, understandings, or agreements regarding the Licensed Material not stated herein are separate from and independent of the terms and conditions of this Public License.

Section 8 – Interpretation. <br>
a.	For the avoidance of doubt, this Public License does not, and shall not be interpreted to, reduce, limit, restrict, or impose conditions on any use of the Licensed Material that could lawfully be made without permission under this Public License. <br>
b.	To the extent possible, if any provision of this Public License is deemed unenforceable, it shall be automatically reformed to the minimum extent necessary to make it enforceable. If the provision cannot be reformed, it shall be severed from this Public License without affecting the enforceability of the remaining terms and conditions. <br>
c.	No term or condition of this Public License will be waived and no failure to comply consented to unless expressly agreed to by the Licensor. <br>
d.	Nothing in this Public License constitutes or may be interpreted as a limitation upon, or waiver of, any privileges and immunities that apply to the Licensor or You, including from the legal processes of any jurisdiction or authority. <br>
