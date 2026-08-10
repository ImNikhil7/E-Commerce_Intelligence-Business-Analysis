
# Data Required for Project

1. Business Questions
Which products generate the most revenue?

Which months perform best?

Are there seasonal trends?

Who are the highest-value customers?

Who is at risk of not returning?

Which customer segments spend the most?

Which products have high ratings but low sales?

Which products should be discontinued?

Do discounts increase revenue or only reduce profit?

Which discount ranges perform best?

What will next month's sales look like?

Which products should be restocked?

Can the system recommend business actions?


2. Required Business Information
### Every company has departments. Each department owns data.

### 1️⃣ Customer Domain

What does the company need to know?

- Customer Profile
- Customer Location
- Age
- Gender (if available)
- Join Date
- Purchase History
- Repeat Customer
- Customer Lifetime Value
- Churn Risk
- Preferred Category
- Preferred Payment Method

Notice... Not only
- Customer Name
- Customer ID

Those don't help decisions.

### 2️⃣ Product Domain

The company wants to know

- Product Name
- Category
- Brand
- Selling Price
- Cost Price
- Profit Margin
- Rating
- Stock
- Supplier
- Launch Date
- Product Status

Questions answered

Should we discontinue this product?

Should we increase stock?

### 3️⃣ Sales Domain

Think beyond - Sales Amount.

We also need

- Revenue
- Profit
- Discount
- Tax
- Quantity
- Order Date
- Month
- Quarter
- Year
- Payment Status
- Refund Status

Because later

- Power BI
- ML
- AI

need these.

### 4️⃣ Order Domain

Orders tell stories.

Every order should include

- Order ID
- Customer
- Product
- Quantity
- Order Date
- Shipping Date
- Delivery Date
- Delivery Time
- Order Status

Questions answered

Which deliveries are delayed?

Average delivery time?

### 5️⃣ Inventory Domain

But companies care a lot.

Need

- Current Stock
- Reorder Level
- Warehouse
- Supplier
- Last Restocked
- Stock Value
- Inventory Age

Questions answered

What should we reorder?

What stock is sitting too long?

### 6️⃣ Marketing Domain

This is where businesses spend money.

Need

- Campaign Name
- Campaign Cost
- Campaign Duration
- Discount
- Coupon Used
- Source

Questions answered

Which marketing campaign made money?

### 7️⃣ Review Domain

Need

- Rating
- Review Text
- Sentiment
- Review Date
- Helpful Votes

Questions answered

Why are customers unhappy?

### 8️⃣ Payment Domain

Need

- Payment Method
- Payment Status
- Transaction ID
- Refund

Questions answered

Which payment methods fail most?

### 9️⃣ Geography Domain

Need

- Country
- State
- City
- Region

Questions answered

Where should we open a warehouse?

### 🔟 Time Domain

Time is one of the most important dimensions.

Need

- Day
- Week
- Month
- Quarter
- Year
- Weekend
- Festival Season

Questions answered

When do customers buy the most?

### 1️⃣1️⃣ AI Domain (Our Unique Feature)

create data for AI.

Need

- Business Recommendation
- Risk Score
- Demand Prediction
- Churn Probability
- Product Score
- AI Summary


### 12 Seller Domain

Seller information

3. Why Each Information Category Is Needed

To know more about the trends and pattern for each domain.

| Domain    | Business Purpose                                                   |
| --------- | ------------------------------------------------------------------ |
| Customer  | Understand customer behavior, loyalty, and churn risk.             |
| Product   | Identify high-performing and underperforming products.             |
| Sales     | Measure revenue, profit, and seasonal trends.                      |
| Orders    | Analyze order lifecycle and operational efficiency.                |
| Inventory | Prevent stock-outs and reduce excess inventory.                    |
| Marketing | Measure campaign effectiveness and ROI.                            |
| Reviews   | Understand customer satisfaction and product quality.              |
| Payments  | Analyze payment success rates and refund trends.                   |
| Geography | Compare regional performance and identify expansion opportunities. |
| Time      | Discover seasonal patterns and sales trends.                       |
| AI        | Generate predictions and business recommendations.                 |


4. Expected KPIs 

- Sales KPIs

Total Revenue

Monthly Revenue

Revenue Growth %

Average Order Value

Total Orders


- Product KPIs

Best Selling Products

Worst Selling Products

Product Rating

Category Performance


- Customer KPIs

Repeat Purchase Rate

Customer Lifetime Value

Churn Rate

Average Customer Spend


- Inventory KPIs

Inventory Turnover

Stock Availability

Slow-moving Inventory


- Marketing KPIs

Discount Effectiveness

Campaign ROI

Conversion Rate (future if campaign data is available)


- AI KPIs

Forecast Accuracy

Churn Prediction Accuracy

Recommendation Acceptance Rate (future enhancement)



5. Possible Data Sources

| Source           | Example                                                              |
| ---------------- | -------------------------------------------------------------------- |
| Public Dataset   | Kaggle                                                               |
| API              | DummyJSON, Fake Store API                                            |
| Web Scraping     | Amazon (only if legally and technically appropriate), Flipkart, etc. |
| Internal Systems | ERP, CRM, POS Database                                               |
| Cloud Storage    | AWS S3, Azure Blob                                                   |
| Database         | MySQL, PostgreSQL                                                    |

