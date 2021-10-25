### Hey! I'm Andrew. Welcome to my [Github] 👋

- 📊 Data visualization is my forte. See my [Tableau] page! 
- 🚀 Most of what you see here is Tableau, Python, and Figma
- 🧠 I'm interested in how our social climate and media trends influence marketing needs
- ⛳ A nice quote: "If it's worth doing, it's worth doing well"

## XYZ Marketing Campaign Correlation Matrix

 
![](Dashboard_Screenshots/dashboard.jpg)
 
This readme includes various screenshots, but you can view the interactive dashboard [here].
 
The dataset was taken from Kaggle, thanks to user [JackDaoud]:
>**The is a CSV file of 2240 observations (customers) with 28 variables related to marketing data.** 
>More specifically, the variables provide insights about:
>
>- Customer profiles
>- Products purchased
>- Campaign success (or failure)
>- Channel performance

## Approach




All in all, these are the dataframes we need to create in Python

| Dataframe | Description |
| :----------- | :----------- |
| productsdf | Sum of numerical values, intended for simple Tableau bar chart |
| shopdf | Not formatted for Tableau, is used to create shopmatrixdf |
| shopmatrixdf | shopdf with .melt applied, is properly formatted for corr. matrix in Tableau |

1. We know that we'll want to use this data to create a correlation matrix in Tableau. But first, we need to clean and restructure our data. We started by importing the dataset and calling it **'shopdf'**.
2. **Cleaning** is very straightforward in this project. First, we take inventory of our dataset and look over our datatypes. We strip whitespace where necessary, convert Income values to float, and convert Dt_customer to datetime. Additionally, we use Birthdate to create a brand new Age column with a simple difference calculation.
3. **Restructuring** includes renaming and rearranging columns, creating **'productsdf'**, and recategorizing Marital Status values (see *notebook* for more info).
4. In order to create a many-to-many correlation matrix with our cleaned data (**'shopdf'**), we would need to use multiple pivots in Tableau to restructure our columns. Tableau only allows for a single pivot, so instead, we opt to use the .melt function while we're still in Python to create a new, Tableau-friendly dataframe: **'shopmatrixdf'** 
5. Once our three dataframes were exported, Tableau and Figma were used in tandem to create the complete [dashboard]. 


## Data Insights
 
![](Dashboard_Screenshots/campaign.png)
 
**Each campaign has its own strengths and weaknesses** 
- Campaigns 1 and 5
    Strong inverse correlation with website views 
    TOF: Keep submission forms local to Facebook/Instagram/etc.
    BOF: Capture leads, opt for email marketing for conversions
- Campaign 3 related to increase of web visits, but not web sales (TOF, eval with CPM)
- Campaign 4 was more likely to convert via web (BOF, eval with CPC)
 
![](Dashboard_Screenshots/demographics.png)
 
**Come for the wine, stay for everything else** 
Wine sales are greater than the sales of all other categories combined
Sales of all product types were less likely among customers with children
Incentivize spending for these customers
Are they more/less likely to be interested in customer rewards programs?
Basket size is an important metric that we don’t have
Large basket sizes may compensate for less frequent visits (see: website visits)
     
![](Dashboard_Screenshots/product.png)
 
**What about the children? Less is more** Strong inverse correlation between children at home and most* KPIs
*All types of product sales and most campaign responses
Customers with no children are preferable
Perform a segmented analysis with more specific data
Calculate and compare CLV/CAC per customer segment
     
![](Dashboard_Screenshots/channel.png)
**Diversify online presence; gain performance insights**
Younger customers with lower incomes are more likely to purchase online and use discounts
Correlation supports the sample’s receptiveness to discounts
Sparse web visits may be linked to low email list open rates
Solve with a value-add: Include promo codes with marketing emails
Encourage activity across multiple channels
Web traffic may be a weak point and may require improvement
 
**Campaign Type:**
Campaign 6 was responsible for most of our sales conversions by a margin of 200%. But for a few different reasons, the conclusions we can draw from this knowledge are limited by the depth of our dataset. We're now encouraged to ask new questions:

- What were the types of each campaign? If 6 was our only sales conversion campaign, and others were lead gen or engagement campaigns, then our limited breadth of metrics are apples and oranges.

- When did these campaigns start and end? Use this information to filter sales metrics by concurrent campaign response data.
 
![](Dashboard_Screenshots/moving_forward.png)
 
**Marital Status:** The importance of marital status as a metric is its pertinence to detailed targeting in FB/IG ads. We can target a few different types of relationship statuses, however our dataset includes some undesirable/ambiguous values.

In addition to Married and Single, we have:

- Together
- Divorced
- Widowed
- Alone
- Absurd
- Yolo

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
