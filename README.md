### Hey! I'm Andrew. Welcome to my [Github] 👋

- 📊 Data visualization is my forte. See my [Tableau] page! 
- 🚀 Most of what you see here is Tableau, Python, and Figma
- 🧠 I'm interested in how our social climate and media trends influence marketing needs
- ⛳ A nice quote: "If it's worth doing, it's worth doing well"

## XYZ Marketing Campaign Correlation Matrix

 
![](Dashboard_Screenshots/dashboard.jpg)
 
This readme includes various screenshots, but you can view the interactive dashboard [here].
 
The dataset was taken from Kaggle, thanks to user [JackDaoud].

## Approach
**The is a CSV file of 2240 observations (customers) with 28 variables related to marketing data.** 
More specifically, the variables provide insights about:

- Customer profiles
- Products purchased
- Campaign success (or failure)
- Channel performance



All in all, these are the dataframes we need to create in Python

| Dataframe | Description |
| :----------- | :----------- |
| productsdf | Sum of numerical values, intended for simple Tableau bar chart |
| shopdf | Not formatted for Tableau, is used to create shopmatrixdf |
| shopmatrixdf | shopdf with .melt applied, is properly formatted for corr. matrix in Tableau |

1. We know that we'll want to use this data to create a correlation matrix in Tableau. But first, we need to clean and restructure our data. We started by importing the dataset and calling it **'shopdf'**.
2. **Cleaning** is very straightforward in this project. First, we took inventory of our dataset and looked over our datatypes. We stripped whitespace where necessary, converted Income values to float, and converted Dt_customer to datetime. Additionally, we used Birthdate to create a brand new Age column with a simple difference calculation.
3. **Restructuring** included renaming and rearranging columns, creating **'productsdf'**, and recategorizing Marital Status values (see *notebook* for more info).
4. In order to create a many-to-many correlation matrix with our cleaned data (**'shopdf'**), we would need to use multiple pivots in Tableau to restructure our columns. Tableau only allows for a single pivot, so instead, we opted to use the .melt function while we're still in Python to create a new, Tableau-friendly dataframe: **'shopmatrixdf'** 
5. Once our three dataframes were exported, Tableau and Figma were used in tandem to create the complete [dashboard]. 


## Data Insights
 
![](Dashboard_Screenshots/campaign.png)
 
**Demographics:** Our analysis points to a predominantly family-focused, upper middle class population who are likely to have multiple children and live in the Pacific Northwest. Genders are equally represented, slightly favoring married couples, and strongly favoring a college education.
 
![](Dashboard_Screenshots/demographics.png)
 
**Location:** Destination-specific content can be A/B tested on the creative level.

    1. Imagery featuring recognizable locations may pique the interest of top-of-funnel colder customers (Crissy Field, Mount Rainier, etc.)

    2. PNW cities like San Francisco, Portland, and Vancouver are known to be well-traveled by commuters riding bikes to-and-from work, which surely makes up a considerable portion of Road Bike and Touring Bike purchases.

    3. The Seattle to Portland (STP) Bicycle Classic is one of the largest recreational bike rides in the country. Each year, thousands of riders participate in this multi-day event. With 77% of our customers in the PNW, the STP poses a potential partnership opportunity, or at the very least, viable inspiration for advertisements.
     
![](Dashboard_Screenshots/product.png)
 
**Age:** The age range of 40-65 is particularly responsive to Facebook Ads but is most likely not using TikTok or Instagram. In order to target this population properly via Facebook:

    1. Create 1-2% lookalike audiences via Facebook Ads from an email list, or from the followers of competitors like REI, MEC, and Cannondale. 

    2. These audiences should match at least 1000 people in the market, and be combined with detailed targeting on the ad set level for use in Messages or Lead Generation campaigns.

    3. A/B test on the creative level with casual family-oriented biking imagery and copy. 

    4. These will be top-of-funnel campaigns, so cost will be measured based on CPM.
     
![](Dashboard_Screenshots/channel.png)
 
**Campaign Type:**
Campaign 6 was responsible for most of our sales conversions by a margin of 200%. But for a few different reasons, the conclusions we can draw from this knowledge are limited by the depth of our dataset. We're now encouraged to ask new questions:

• What were the types of each campaign? If 6 was our only sales conversion campaign, and others were lead gen or engagement campaigns, then our limited breadth of metrics are apples and oranges.

• When did these campaigns start and end? Use this information to filter sales metrics by concurrent campaign response data.
 
![](Dashboard_Screenshots/moving_forward.png)
 
**Marital Status:** The importance of marital status as a metric is its pertinence to detailed targeting in FB/IG ads. We can target a few different types of relationship statuses, however our dataset includes some undesirable/ambiguous values.

In addition to Married and Single, we have:

• Together
• Divorced
• Widowed
• Alone
• Absurd
• Yolo

There is no documentation to elaborate on the meaning of these values. While some remote inferences can be made, they were grouped into a collective Other category for the sake of consistency.

## In Hindsight

This was an earlier project of mine. If I were to approach this project with the experience that I have now, the main difference I'd make in my actions is with the dashboard design. There are a number of ways I could go about making it more intuitive, organized, and aesthetically pleasing. For example, it would be beneficial to add separate dashboard pages or show/hide buttons to reduce clutter. This is a lot of information to squeeze into a 1600x900px space.

I've noticed that the most successful dashboards are the easiest to digest. Overall, I enjoy the monochrome color palette and the variety of graphs/charts that I included.  Marketing/BI analysts should have no problems using my dashboard. But looking back, I've realized that I've gained plenty of experience since working on this. It's been a refreshing way to take note of what I should do differently next time around.

I may revisit this in the future! If I do, I'll include before and after images.

## See the complete interactive dashboard [here]

</details>

[Tableau]: https://public.tableau.com/app/profile/andrew.bruening
[Github]: https://github.com/andrewbruening
[here]: https://public.tableau.com/views/MarketingCampaignCorrelationMatrix/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link
[dashboard]: https://public.tableau.com/views/MarketingCampaignCorrelationMatrix/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link
[JackDaoud]: https://www.kaggle.com/jackdaoud/marketing-data
