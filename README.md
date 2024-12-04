### Description

This Python script processes Premier League table data scraped from the official website. The script focuses on cleaning, transforming, and encoding the data to prepare it for machine learning models or analytical tasks.



### Key Features

1. **Data Extraction and Initial Processing**:
   - Scrapes the Premier League table data directly from the official website using `pandas.read_html`.
   - Filters and cleans the dataset by removing unnecessary rows and resetting the index.

2. **Data Cleaning**:
   - Removes redundant columns like `index`, `Unnamed: 12`, and others after extracting useful information.
   - Splits and transforms the `Position  Pos` column to extract the team's position in the table.

3. **Feature Engineering**:
   - Extracts team abbreviations (`Abb`) and full team names (`Team`) from the `Club` column using regular expressions.
   - Splits and organizes match form data (`Form`) into multiple features such as:
     - `Win form`
     - `Win Day`
     - `Date`
     - `Month`
     - `Year`
   - Creates a new feature (`Next Match`) based on the `Next` column.

4. **Column Rearrangement**:
   - Ensures logical grouping of columns for better readability and structure.

5. **Categorical Encoding**:
   - Performs **One-Hot Encoding** on features such as `Month`, `Win form`, and `Win Day` to convert them into numerical values suitable for machine learning models.
   - Applies **Label Encoding** to features like `Team`, `Next Match`, and `Abb` for additional transformation.

6. **Final Data Transformation**:
   - Combines the encoded features with the cleaned dataset to create the final DataFrame (`Final_df`) ready for analysis or modeling.


### Use Case

This script is designed for:
- **Sports analytics**: Gaining insights from Premier League data, such as team performance, match trends, or predictive modeling for future matches.
- **Machine learning preparation**: Preparing league data for predictive tasks like win predictions or player/team performance analysis.

### Notes
- The script handles data directly from a dynamic web source, making it adaptable to updates in league standings.
- Encoded features ensure compatibility with most machine learning models.
