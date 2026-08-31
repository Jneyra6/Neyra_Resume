## dbt Data Pipeline

To support campaign activation and performance measurement, I developed a dbt pipeline within Snowflake that identified season pass holders with zero or one park visit during the operating season. The pipeline transformed transactional sales and visitation data into a reporting-ready audience dataset used for marketing outreach and ongoing campaign analysis.

### Pipeline Architecture

The solution leveraged a layered dbt architecture consisting of:

#### Source Data

- Sales transactions
- Season pass redemptions
- Product dimension data
- Park dimension data

#### Staging Models

- `stg_prod_sales`
- `stg_prod_redemptions`

These models standardized source data structures, applied data quality checks, and prepared datasets for downstream transformations.

#### Intermediate Layer

- `int_sales_joined_redemptions`

This model combined season pass purchase activity with redemption behavior, creating a customer-level view of season pass utilization.

#### Final Output

- `main_zero_one_snapshot`

The final model generated a campaign-ready audience snapshot containing season pass holders who had visited a park either zero or one time during the season.

### Business Logic

The pipeline was designed to:

- Identify low-engagement season pass holders.
- Calculate customer visitation frequency.
- Segment customers into 0-visit and 1-visit audiences.
- Support marketing consent-based targeting strategies.
- Generate reporting datasets for campaign monitoring and performance measurement.

### dbt Lineage

The following lineage graph illustrates the flow of data from source systems through staging and transformation layers into the final campaign audience dataset.

![dbt Lineage](images/dbt_lineageess Impact

The resulting audience dataset supported a retention-focused campaign targeting more than 200,000 season pass holders who had received limited value from their pass purchase.

The data products created through this pipeline enabled:

- Email campaign activation for opted-in customers.
- Paid social media audience targeting for opted-out customers.
- Automated audience generation and campaign reporting.
- Ongoing visitation tracking throughout the campaign period.

### Technologies Used

- Snowflake
- dbt
- SQL
- Dynamic Tables
- Customer Analytics
- Audience Segmentation
- Marketing Measurement
- Analytics Engineering
