# Salary Analysis by Job Title

This project analyzes the salary distributions by job title using a given dataset. The analysis involves calculating the average salary for each job title and visualizing the top 10 job titles by average salary using different color schemes.

## Requirements

- Python 3.x
- pandas
- matplotlib
- seaborn
- jupyter

## Installation

1. Clone the repository or download the project files.
2. Install the required Python packages using pip:
   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```

## Usage

1. Run the Jupyter Notebook:
   ```bash
   jupyter notebook nt_1.ipynb
   ```
2. Execute the cells in the notebook to perform the analysis and generate the plots.

## Analysis Steps

The notebook follows these steps for the analysis:

1. **Load the dataset**:
   ```python
   df = pd.read_csv('/mnt/data/your_dataset.csv')  # Replace with the correct path to your dataset
   ```

2. **Calculate the average salary for each job title**:
   ```python
   mean_salary = df.groupby('job_title')['salary_in_usd'].mean().reset_index()
   ```

3. **Get the top 10 job titles by average salary**:
   ```python
   top_10_jobs = mean_salary.nlargest(10, 'salary_in_usd')
   ```

4. **Sort the job titles for better visualization**:
   ```python
   top_10_jobs = top_10_jobs.sort_values(by='salary_in_usd')
   ```

5. **Plotting**:
   - Using the "viridis" color palette:
     ```python
     plt.figure(figsize=(12, 5))
     sns.barplot(x='salary_in_usd', y='job_title', data=top_10_jobs, palette='viridis')
     plt.title('Average Salary in USD by Job Title for Top 10 Most Common Job Titles')
     plt.xlabel('Average Salary in USD')
     plt.ylabel('Job Title')
     plt.show()
     ```

## Results

The notebook produces a bar plot showing the average salary in USD by job title for the top 10 most common job titles, using the "viridis" color palette.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.

