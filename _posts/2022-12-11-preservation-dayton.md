---
layout: post
title: Preservation Dayton Conversation
---

Thanks again to Monica Snow for visiting and discussing [Preservation Dayton](https://www.preservationdayton.com/). I'm excited to see how we can help them with their mission to preserve the historical building and neighborhoods in the Dayton area.

Ms. Snow laid out three tasks that we could help with:

* Document the properties in Dayton where the taxes owed are greater than the assessed value of the property.

* Document the vacant and tax delinquent properties in Dayton.

* Help them update the data for the [The Recommendations of the Landmark Preservation Task Force: A Report](https://www.preservationdayton.com/uploads/4/5/9/0/4590030/final_report_landmark_preservation_task_force.pdf).

For the first task, there are a handful of newly created issues in Github to work toward this goal, including [scrapers/26](https://github.com/codefordayton/scrapers/issues/26), [scrapers/27](https://github.com/codefordayton/scrapers/issues/27), [montylots/4](https://github.com/codefordayton/montylots/issues/4), and [montylots/5](https://github.com/codefordayton/montylots/issues/5). If you have any questions please drop a note on the issue or in Discord!

We are on hold on the second task. Ms. Snow believes they have access to this data. If so, she will provide it to us. As a worst case, we could acquire the data from [Regrid](https://regrid.com/) for a small fee.

The third task requires a bit more explaining. The data that needs to be updated is the data in Appendix 2 (pg 12 of the report). The original report covered data from 1996 to 2012. We should update that to 2022 data. The most difficult part of this task will require identifying the properties that are in each neighborhood. This task can likely be done by pulling a Montgomery County Auditor's data file and parsing the NBHD values.

This is also an opportunity to update the infrastructure for these projects. The code for monty lots is split across 3 repositories:

1. [Scrapers](https://github.com/codefordayton/scrapers): This is where the various Code for Dayton Web Scrapers lived. The Monty Lots scraper is the [reap_spider](https://github.com/codefordayton/scrapers/blob/master/dayton/spiders/reap_spider.py). This was used to supplement files downloaded from the Montgomery County Auditor's site. The [scrape.sh](https://github.com/codefordayton/scrapers/blob/master/scrape.sh) file represents rudimentary orchestration of the process.

2. [DaytonReap](https://github.com/codefordayton/daytonreap): This is the old LotLinker repository. The python scripts necessary for geocoding and creating the json file are located here. These are ripe for moving into the scrapers project.

3. [MontyLots](https://github.com/codefordayton/montylots): The static site for MontyLots. The site is fairly simple javascript site with a leaflet map, but a lot can be done with it if we build out the infrastructure some.

If something on this list strikes your fancy, but you don't see an issue, reach out on Discord! We'd love to have your help!

- Dave

