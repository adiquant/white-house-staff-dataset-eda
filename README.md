# White House Staff Salaries [2017-2020]

Cleaned and complete WH staff dataset (salary, gender, title) for 6 terms, and a Jupyter Lab EDA.


## Context

While many public datasets documented the White House Office staff data, there is not a complete or correct version for the last 4 administrations. Those data points are usually scattered across different websites and formats. A thorough data collection and processing has been done to make your life easier.

The main source document used in data assessment is the Annual Report to Congress on White House Office Staff. Since 1995, the White House has been required to deliver a report to Congress, listing the title and salary of every White House Office employee. This report also contains the title and salary details of administration officials who work at the Office of Policy Development, including the Domestic Policy Council and the National Economic Council - along with White House Office employees. It does not include staff members of the Office of Management and Budget, household staff, military attaches, or all of the Office of Vice President staff. 


## Content

This dataset contains a folder of cleaned yearly data and 3 files:
* wh_staff_dataset.csv - Complete WH staff data from 1997 to 2020.
* cpi_dataset.csv - Inflation info for EDA.
* why.jpg - WH logo.

Row values include following attributes:
* year - Year of employment, as an integer [1997-2020].
* name - Staffer name, formated as <last_name><comma><first_name>. Last and first names can consist of multiple names, separated by a space. If the staffer has a suffix (Jr., Sr., I, II, III, IV), it is added last, separated by a comma: <last_name><comma><first_name><comma><suffix>.
* gender - Staffer gender. Can be Male, Female, or NA. Gender is mostly interpolated from the first name. Names with a similar probability of being male and female have been checked manually.
* status - Staffer employment status. Can be Employee, Employee (part-time), Detailee, or NA.
* salary - Staffer salary in nominal US Dollars. Represented as an integer, without a dollar ($) character and trailing zeros. 
* pay_basis - Pay basis. Can be Per Annum, Per Diem, or NA.
* position_title - Staffer position title name. They require more work to be fully usable, since administrations have different names for the same title, and some people have multiple titles - needs to be normalized in the future.

- Note about missing values
Some fields are omitted in official reports. Not sure if the NAs are just a mistake, a secret, or vaccant positions, but I included them in the dataset for the sake of completeness. 
Even though some names are missing (in 2004 and 2006) they are alphabetically sorted in the official report so the last name initial can be inferred.


## Acknowledgements

This dataset was collected from multiple sources, in various formats.
* Trump Data (2017-2020) - This data only exists in PDF and can currently be downloaded on the [official White House website](https://www.whitehouse.gov/staff-salaries). Tabula was used to extract it into CSV for processing.
* Obama Data (2009-2016) - This data was released as CSV. Most of it can be found on the [archives.gov website](https://obamawhitehouse.archives.gov/briefing-room/disclosures/), but not everything (2010 and 2011 are missing, and 2009 is a PDF). Since it was formerly available as CSV, those files can be found all over the internet. [Source_1](https://public.opendatasoft.com/explore/dataset/white-house-salaries/table/)(This dataset contains information pertaining to the salaries of all White House Executive Office of the President employees since 2001, from President Bush to President Trump.), [Source_2](https://github.com/helloworlddata/white-house-salaries/tree/master/data/raw), [Source_3_2010](https://www.fedsmith.com/wp-content/uploads/2010/11/2010_Report_to_Congress_on_White_House_Staff.xls), [Source_4_2011](https://spreadsheets.latimes.com/white-house-salaries/)
* Bush Data (2001-2008) - This data was found on the [George Bush Library website](https://www.georgewbushlibrary.smu.edu/Digital-Library---2/~/link.aspx?_id=0220C938E5F64BFFB55047721E134E99). All files are in PDF, mostly scanned files. Again, I used Tabula to get it into CSV, and then cleaned it with a combination Excel, Python scripts, Tableau Prep, and manual labour. Tabular machine-readable data for some years was found on the old Washington Post website ([2001](https://www.washingtonpost.com/wp-srv/onpolitics/transcripts/whitehousesalaries.htm), [2003](https://www.washingtonpost.com/wp-srv/politics/administration/whbriefing/stafflistb.html), [2004](https://www.washingtonpost.com/wp-srv/politics/administration/whbriefing/2004stafflistb.html), [2005](https://www.washingtonpost.com/wp-srv/politics/administration/whbriefing/2005stafflistb.html), [2006](https://www.washingtonpost.com/wp-srv/opinions/graphics/2006stafflistsalary.html), [2007](https://www.washingtonpost.com/wp-srv/opinions/graphics/2007stafflistsalary.html), [2008](https://www.washingtonpost.com/wp-srv/opinions/graphics/2008stafflistsalary.html)). That data was used as a base, validated by the parsed PDF data. Turns out the Washington Post data was also parsed PDF data, so they had some smaller mistakes as well. Cobining them fixed the issues.
* Clinton Data (1997-2000) - Among the FOIA WH personnel materials on the [George Bush Library website](https://www.georgewbushlibrary.smu.edu/Digital-Library---2/~/link.aspx?_id=0220C938E5F64BFFB55047721E134E99) there were scanned reports of the Annual Report to Congress on White House Staff for 1997, 1998, 1999, and 2000. Those were pretty messy but cleaned up well. There might be somewhere on the Clinton Presidenital Library webpage a record for the same report from 1993 to 1996 (at least for 1995 and 1996), but I couldn't find it. I would appreciete it if someone could help me on that front.


## Inspiration

The White House staff data can be used for exploratory data analysis projects. It is not viable for tracking precise turnover rates since it's issued only once per year - it guarantees staff on payroll from mid June to start July, but doesn't show employment out of that period.


## History:
* Version 1: Initial commit.
* Version 2: TBD