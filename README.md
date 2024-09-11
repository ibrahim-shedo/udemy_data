Udemy Courses Data Analysis
This project aims to analyze Udemy course data using Python and Pandas to extract key insights related to the subjects, pricing models, subscribers, and course details. The dataset provides information about Udemy's diverse course offerings, including course IDs, titles, pricing, levels, and subject categories.

Table of Contents
Project Overview
Dataset Information
Analysis Questions
Installation and Setup
Data Analysis Steps
Visualizations
Conclusion
Future Enhancements
Project Overview
This project involves analyzing Udemy's course dataset to uncover valuable insights. Using Python and Pandas, we answer several specific business-related queries, such as identifying the most popular courses, price distributions, and trends based on course publication dates. The analysis also focuses on key metrics such as the number of subscribers, course levels, and subject distribution.

Dataset Information
The dataset used in this project contains various details about Udemy courses:

Column Name	Description
course_id	Unique identifier for each course
course_title	Title of the course
is_paid	Indicates if the course is paid or free
price	Price of the course (for paid courses)
num_subscribers	Number of students enrolled in the course
num_reviews	Number of reviews provided by students
num_lectures	Total number of lectures included in the course
level	Course difficulty level (Beginner, Intermediate, Expert)
content_duration	Total duration of the course content (in hours)
published_timestamp	Date when the course was published
subject	Subject category of the course (e.g., Business, Design, Development)
Dataset Source
The dataset can be downloaded from Udemy Course Dataset Source. (Insert dataset link)

Analysis Questions
The following key questions are addressed in this analysis:

What are the different subjects Udemy offers?
Which subject has the maximum number of courses?
Show all paid courses.
Show all free courses.
What are the top 10 selling courses?
What are the least 5 selling courses?
Show all Graphic Design courses with fewer than 100 subscribers.
List all courses related to Python.
What are the courses that were published in 2015?
What is the maximum number of subscribers for each course level (Beginner, Intermediate, Expert)?
Installation and Setup
To run this project locally, follow these steps:

Prerequisites
Python 3.x
Pandas library
Jupyter Notebook (optional, for interactive analysis)
Matplotlib/Seaborn (optional, for visualizations)
Install Dependencies
Clone the repository:

bash
Copy code
git clone https://github.com/your-username/udemy_dcourses_data.git
cd udemy_dcourses_data
Create a virtual environment (optional but recommended):

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install the required packages:

bash
Copy code
pip install -r requirements.txt
Launch Jupyter Notebook (if preferred):

bash
Copy code
jupyter notebook
Data Analysis Steps
1. Load the Data
python
Copy code
import pandas as pd

# Load dataset
df = pd.read_csv('udemy_courses.csv')

# Quick overview of the dataset
df.info()
df.head()
2. What are the different subjects Udemy offers?
python
Copy code
unique_subjects = df['subject'].unique()
print("Subjects offered by Udemy: ", unique_subjects)
3. Which subject has the maximum number of courses?
python
Copy code
subject_counts = df['subject'].value_counts()
print(f"Subject with the most courses: {subject_counts.idxmax()}")
4. Show all paid courses
python
Copy code
paid_courses = df[df['is_paid'] == True]
paid_courses.head()
5. What are the top 10 selling courses?
python
Copy code
top_selling_courses = df.sort_values('num_subscribers', ascending=False).head(10)
top_selling_courses[['course_title', 'num_subscribers']]
(Include other queries and analysis questions with appropriate code snippets)

Visualizations
To make the analysis more intuitive, we can include visualizations such as:

Top 10 Courses by Subscribers
Price Distribution Across Courses
Subscribers vs. Course Levels
Courses Published per Year
Example of a simple bar chart:

python
Copy code
import matplotlib.pyplot as plt

# Top 10 courses by number of subscribers
top_10 = df.sort_values(by='num_subscribers', ascending=False).head(10)
plt.figure(figsize=(10,6))
plt.barh(top_10['course_title'], top_10['num_subscribers'])
plt.xlabel('Number of Subscribers')
plt.title('Top 10 Selling Courses')
plt.show()
Conclusion
This analysis of Udemy course data provides valuable insights into the platform's subject offerings, popular courses, and pricing strategies. We identified key trends such as the most popular subjects, the top-selling courses, and the distribution of free vs. paid courses. The analysis also highlights important trends for course creators, such as which subjects attract the most students and the ideal pricing models.

Future Enhancements
Advanced Data Analysis: Explore correlations between price, content duration, and number of subscribers.
Text Mining: Perform sentiment analysis on course reviews to determine factors that drive higher ratings.
Predictive Modeling: Build a machine learning model to predict the success of a course based on features like price, duration, and subject.
Dashboard: Create an interactive dashboard using Plotly or Dash to visualize key metrics dynamically.
License
This project is licensed under the MIT License. See the LICENSE file for details.

