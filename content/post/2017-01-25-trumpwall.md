---
title: An alternative to the Mexico-US wall where the US would gain millions of dollars
tags:
- politics
categories:
- Ideas
date: 2017-01-25T02:00:00Z
---

{{% alert note %}}
tl;dr There is a 600 million to 2 billion USD annual market related to crossing the Mexico-US border. Allow temporary work visas (say 3 years) to take over this market and use the money to boost the US Border Patrol to build a wall of eyes, not a physical wall.
{{% /alert %}}

President Trump of the United States of America,

cc President Peña Nieto of the United Mexican States

Today, Wednesday January 25th 2017, you are expected to announce your plans about building a wall between the United States and Mexico. I am opposed to building that wall but I also believe that providing alternatives is important when disagreeing. With that in mind, let me expose an alternative to your physical wall.

Mexico has a net immigration rate of -1.7 migrants per 1,000 and a population of 123,166,749 individuals[^1] which means that about 209,000 people leave Mexico every year. The Department of Homeland Security 2014 report[^2] shows that 350,177 out of 679,996 (51%) total aliens apprehended are from Mexico (52% reported elsewhere[^3],[^4]). Many of the illegal immigrants pay people for helping them cross the Mexico-US border also known as _coyotes_. Some informal surveys put the cost of a _coyote_ between 3,000 and 20,000 US dollars[^5],[^6]. That means that there is an annual market worth about 627 to 1,050 million US dollars. This market exists and has been steady for years now. A physical wall in the Mexico-US border might not stop the illegal immigration to the US. Loss of jobs in Mexico directly related to your policies might even prompt more people to leave Mexico[^7]. I believe that the high volume of people crossing the Mexico-US border makes it easier for drug cartels to hide and transport drugs. That is, it makes it harder for the US Border Patrol Agents to find who is transporting drugs and the track down the routes they use.

So, what if the US took over this multi million dollar market? I have had the opportunity to visit countries that offer temporary work visas (ranging from 6 months to 3 years). The people interested in these visas have to pay a fee, pass a background check and sometimes go through health screenings. I believe that these immigrants pay the fee because it allows them to legally migrate, work for a while, save some money, and then go back to their home countries. From an immigrant's perspective, it must be very appealing to pay the same amount of money it cost to migrate safely and legally (for temporary work) than to attempt to cross the border illegally with the risk of dying in the process or getting kidnapped. Additionally, I think that temporary workers would feel much safer to go out of their homes while in the US, spending some of their hard earned money in the process and stimulating the local economy. They would be more likely to get a regular job where they would pay income taxes instead of getting payed _under the table_ and dodging the IRS. Furthermore, having the opportunity to legally go back home and visit family would be a huge advantage from an immigrant's perspective.

While writing this letter I realized that the idea of _immigration tariffs_ is not new[^8],[^9],[^10],[^11]. However, I have not heard it being discussed recently and simply ask that you consider it.

To try to convince you that _immigration tariffs_ are an interesting alternative, consider what your government could do with an additional 600 to 1,000 million US dollars a year -- or multiply those numbers by two to get 1.2 to 2 billions USD a year by taking into account that about 50% of illegal immigrants are Mexicans. The average Border Patrol Agent self-reported salary is 80,250 USD a year[^12]. The actual salaries range from 21,616 to 157,257 USD as of January 2017[^13] depending on the _grade_ and _level_ as well as other options[^14]. In 2016, there were nearly 20,000 border patrol agents in the US[^15]. That means that you could decide to increase the number of Border Patrol Agents by 10,000 (50%) for about 803 million USD or increase the number of Agents by 5,000 while increasing their salaries by 10% for about 602 million USD. Why do I bring up the number of Agents? Because that would mean that you are building a **_wall_ of eyes** in the Mexico-US border. I believe that under this scenario, you and your public relations team could convince your supporters that you delivered on your campaign promise of building a wall. It would just be a different kind of wall. The extra Border Patrol Agents and/or happier Agents (due to their increased salary) along with fewer attempts to cross the border (because immigrants would be interested in paying the _immigration tariff_) would make them more efficient in their jobs. Some of them could be dedicated to making sure no one overstays their temporary work visa. Also note that by law, you _have_ to be a US citizen to become a Border Patrol Agent[^16], so you would be increasing US jobs by 5 to 10 thousand under this scenario. That is more than the 700 jobs you claim to have saved from moving to Mexico from the US by cancelling the plans to build a factory in Mexico[^17]. I also imagine that this scenario would boost bus and airplane ticket sales.

I am of the opinion that _immigration tariffs_ would allow many individuals to have hope that they can improve their economic situation for them and their families. It would also translate _hope_ into a specific monetary goal. As of yesterday, 3,000 USD is about 64,000 MXN[^18] that translates to 800 days of minimum wage salary in Mexico[^19]. Saving that amount of money would take over 2 years if the person didn't spend any of their income! While ideally the _immigration tariff_ would be lower than 3,000 USD, ultimately there would be a threshold that opens doors to more economic opportunity. So, Peña Nieto and Mexico have the challenge of showing that Mexicans can stay in Mexico and improve their economical situation if they can save that amount of money to start a small business, advance their education, among other options.

Migration involves two sides and as presidents of two countries of _united states_ (American and Mexican, respectively) I encourage you to keep thinking how to _unitedly_ address migration and take over the multi million dollar market that _coyotes_ currently control.

Best,
Leonardo


<center>
<a href="https://en.wikipedia.org/wiki/Mexican_Americans"><img alt = 'Mexican American flag' width='700' src='https://upload.wikimedia.org/wikipedia/en/3/32/Mexican_American_Flag.PNG' /></a>
</center>

{{% alert warning %}}
This open letter is my opinion only and not that of my employer or other people I know.
{{% /alert %}}

### Calculations used


    ## Mexican immigrants per year
    round(-1.7 * 123.166749) * 1000

    ## [1] -209000

    ## Percent of Mexican illegal immigrants per year
    round(350177 / 679996 * 100)

    ## [1] 51

    ## Range of the coyote market: only Mexicans
    c(209000, 350000) * 3000 / 1e6

    ## [1]  627 1050

    ## Range of the coyote market: everyone
    c(209000, 350000) * 3000 / 1e6 * 2

    ## [1] 1254 2100

    ## Cost of having 10k more Border Patrol Agents
    10000 * 80250 / 1e6

    ## [1] 802.5

    ## Cost of having 5k more Border Patrol Agents while increasing their salary by 10%
    (5000 * 80250 * 1.1 + 20000 * 80250 * 0.1) / 1e6

    ## [1] 601.875

    ## 3000 USD in pesos (rounded to thousands)
    round(3 * 21.4230) * 1000

    ## [1] 64000

    ## Minimum wage days
    round(64000 / 80.04)

    ## [1] 800

    ## Minimum wage years -- without a single break!!!
    round(800 / 365.25, 1)

    ## [1] 2.2

I finally wrote this open letter after my poll a few weeks ago:

{{< tweet 817608772000608256 >}}


### References

[^1]: https://www.cia.gov/library/PUBLICATIONS/the-world-factbook/geos/mx.html
[^2]: https://www.dhs.gov/sites/default/files/publications/ois_yb_2014.pdf
[^3]: http://www.pewresearch.org/fact-tank/2016/11/03/5-facts-about-illegal-immigration-in-the-u-s/
[^4]: https://en.wikipedia.org/wiki/Illegal_immigration_to_the_United_States
[^5]: http://www.univision.com/noticias/inmigracion/el-costo-del-cruce-indocumentado-a-estados-unidos-varia-entre-3-mil-y-20-mil-dolares
[^6]: https://www.bloomberg.com/news/articles/2013-01-20/coming-to-america-its-going-to-cost-you
[^7]: http://www.jornada.unam.mx/ultimas/2017/01/06/cancelacion-de-ford-dejara-a-miles-sin-empleo
[^8]: https://openborders.info/immigration-tariffs/
[^9]: http://theconversation.com/tariffs-could-fix-both-immigration-policy-and-people-smuggling-40972
[^10]: https://cei.org/onpoint/conservative-case-immigration-tariffs
[^11]: https://www.brookings.edu/book/brain-gain/
[^12]: https://www.glassdoor.com/Salary/US-Customs-and-Border-Protection-Salaries-E41481.htm
[^13]: https://www.opm.gov/policy-data-oversight/pay-leave/salaries-wages/salary-tables/pdf/2017/LR.pdf
[^14]: http://work.chron.com/salary-law-enforcement-border-patrol-person-3148.html
[^15]: https://www.cbp.gov/sites/default/files/assets/documents/2017-Jan/USBP%20Stats%20FY2016%20sector%20profile.pdf
[^16]: http://www.criminaljusticedegreeschools.com/criminal-justice-careers/border-patrol-agent/
[^17]: http://www.foxnews.com/politics/2017/01/03/ford-to-scrap-mexico-plant-invest-in-michigan-due-to-trump-policies.html
[^18]: http://www.banxico.org.mx/portal-mercado-cambiario/
[^19]: http://www.sat.gob.mx/informacion_fiscal/tablas_indicadores/Paginas/salarios_minimos.aspx
