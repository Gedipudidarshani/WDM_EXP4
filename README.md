### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 14-09-2024
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
import pandas as pd
# Visitor segmentation based on characteristics
# read the data
visitor_df = pd.read_csv('/content/clustervisitor.csv')

# Perform segmentation based on characteristics (e.g., age groups)
age_groups = {
    'Young': (visitor_df['Age'] <= 30),
    'Middle-aged': ((visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50)),
    'Elderly': (visitor_df['Age'] > 50)
}
print(age_groups)
for group, condition in age_groups.items():
    visitors_in_group = visitor_df[condition]
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
    print()
```
### Output:
![image](https://github.com/user-attachments/assets/ef21667d-566d-4fca-bfa8-ad4363b3b95d)
![image](https://github.com/user-attachments/assets/b35a62cc-bf5a-49db-86fe-32457eb69444)
![image](https://github.com/user-attachments/assets/3aee559d-cefa-418b-a7c3-7cde0075bd8b)
![image](https://github.com/user-attachments/assets/845b52dc-1a79-4a08-bf86-1fb7188df45d)

### Visualization:
```python
# Create a list to store counts of visitors in each age group
visitor_counts = []

# Count visitors in each age group
for group, condition in age_groups.items():
  visitors_in_group = visitor_df[condition]
  visitor_counts.append(len(visitors_in_group))
    
# Define age group labels and plot a bar chart
age_group_labels=list(age_groups.keys())

plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/302317f1-c7b2-456a-8d55-77a8bca462ca)


### Result:
Thus,Visitor segmentation based on age groups successfully completed.
