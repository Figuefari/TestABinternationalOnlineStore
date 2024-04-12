## Proyect description

An international online store conducted an A/B test and only provided the technical specifications and test results. 
The purpose is to test changes related to the introduction of an enhanced recommendation system.

## Tasks

1. Describe the study objectives.
2. Explore the data.
3. Conduct exploratory data analysis.
   - Study conversion at different stages of the funnel.
   - Distribution of events across days.
   - Events per user.
4. Evaluate the results of the A/B test.
5. Conclusions and recommendations.

## Technical Description of the Test

- Test Name: `recommender_system_test`
- Groups: A (control), B (new payment funnel)
- Launch date: 2020-12-07
- Date of stopping new user acceptance: 2020-12-21
- Completion date: 2021-01-01
- Audience: 15% of new users from the EU region
- Purpose of the test: to test changes related to the introduction of an enhanced recommendation system
- Expected Outcome: within 14 days after sign-up, users will show improved conversion in product page views (event `product_page`), instances of adding items to the shopping cart (`product_card`), and purchases (`purchase`). At each stage of the funnel `product_page → product_card → purchase`, there will be at least a 10% increase.
- Expected number of test participants: 6,000

## Data Description (4 files):

- `ab_project_marketing_events_us.csv`: marketing events calendar for 2020
- `final_ab_new_users_upd_us.csv`: all users who registered on the online store from December 7 to December 21, 2020
- `final_ab_events_upd_us.csv`: all events of new users in the period from December 7, 2020, to January 1, 2021
- `final_ab_participants_upd_us.csv`: table with data of test participants

### Structure of `ab_project_marketing_events_us.csv`:

- `name`: name of the marketing event
- `regions`: regions where the advertising campaign will take place
- `start_dt`: start date of the campaign
- `finish_dt`: end date of the campaign

### Structure of `final_ab_new_users_upd_us.csv`:

- `user_id`
- `first_date`: registration date
- `region`
- `device`: device used for registration

### Structure of `final_ab_events_upd_us.csv`:

- `user_id`
- `event_dt`: date and time of the event
- `event_name`: name of the event type
- `details`: additional data about the event (e.g., total order amount in USD for `purchase` events)

### Structure of `final_ab_participants_upd_us.csv`:

- `user_id`
- `ab_test`: test name
- `group`: the test group to which the user belonged

## Contents

1. Initialization
    - Test background.
    - Library loading.
    - Data loading.
 
2. Exploratory Data Analysis
    - Data overview.
    - Data description.
    - Visualization of sample data.
    - Data distribution.
    - Missing values.
    - Outliers.
    - Preprocessing preliminary conclusions.
    
3. Preprocessing
    - Duplicate checking.
    - Missing values handling.
    - Data type conversion.
    - Shared unique users.
    - Test type separation.
    - Correct participants update.
    - Events update.
    - Dataframe merging.
    - Data enrichment.
    - Preprocessing conclusions.
    
4. Data Analysis
    - Data study and verification.
    - Daily activity study.
    - Event funnel study.
    - Experiment results study.
    - Proportion test.
 
5. Final Conclusions

## Used libraries

- pandas
- seaborn
- datetime
- numpy
- plotly
- scipy
- statsmodels
