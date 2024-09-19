# :notebook: PA4 - DATA WRANGLING AND DATA VISUALIZATION

## ECE BOARD EXAM PROBLEM:
**Using data wrangling and data visualization technique with
storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given.**

```python
import pandas as pd

#Read the csv file into the data frame
df = pd.read_csv('board2.csv')
df
```

![image](https://github.com/annoyinglyghost/Images-2-/blob/main/pa4%20csv.png)

---

**1. Create the following data frames based on the format provided:
Example: Vis = [“Name”, “Gender”, “Track”, “Math<70”]; hometown is constant as Visayas**

![image](https://github.com/annoyinglyghost/Images-2-/blob/main/pa4%201.png)

🌱 Input:

```python
# Filter the data where Hometown is Visayas and Math grade is less than 70
Vis = df[(df['Hometown'] == 'Visayas') & (df['Math']<70)].reset_index()
# Select only the needed columns which are Name, Gender, Track, and Math 
Vis = Vis[['Name', 'Gender', 'Track', 'Math']]

# Display the filtered data frame
Vis
```
🌳 Output:

![image](https://github.com/annoyinglyghost/Images-2-/blob/main/pa4%20111.png)

----

**a. Filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as
Instrumentation and hometown Luzon**

🌱 Input:
```python
# Filter the data where: Track=Instrumentation, Hometown=Luzon, Electronics > 70
Instru = df[(df['Track'] == 'Instrumentation') & (df['Hometown'] == 'Luzon') & (df['Electronics'] > 70)].reset_index()
# Select the only needed columns of Name, GEAS, and Electronics
Instru = Instru[['Name', 'GEAS', 'Electronics']]

#Display the results
Instru
```

🌳 Output:

![image](https://github.com/annoyinglyghost/Images-2-/blob/main/pa4%20a.png)

---

**b. Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is
constant as Mindanao and gender Female**

🌱 Input:
```python
# Replacing these with the actual grade columns in your dataset.
grades = ['Math', 'GEAS', 'Electronics', 'Communication'] 

# Adding a new column which is Average and also calculating the average of the grades
df['Average'] = df[grades].mean(axis=1).round(2)

# Filtering the DataFrame for hometown Mindanao, female students, and average >= 55
Mindy = df[(df['Hometown'] == 'Mindanao') & (df['Gender'] == 'Female') & (df['Average'] >= 55)].reset_index()

# Select only the required columns which are Name, Track, Electronics, and Average
Mindy = Mindy[['Name', 'Track', 'Electronics', 'Average']]

# Display the results
Mindy
```
🌳 Ouput:

![image](https://github.com/annoyinglyghost/Images-2-/blob/main/pa4%20b.png)

---

**2. Create a visualization that shows how the different features contributes to average grade. Does
chosen track in college, gender, or hometown contributes to a higher average score?**

🌱 Input:
```python
import pandas as pd
import matplotlib.pyplot as plt

# Calculate the average grade for each student
df['Average'] = df[['GEAS', 'Electronics', 'Math', 'Communication']].mean(axis=1)

# Plotting the results
plt.figure(figsize=(20, 6))

# Plot for Track, Gender & Hometown
plt.subplot(1, 3, 1)
plt.bar(track_avg['Track'], track_avg['Average'], color='lightpink')
plt.title('Average Grade by Track')
plt.xlabel('Track')
plt.ylabel('Average Grade')

plt.subplot(1, 3, 2)
plt.bar(gender_avg['Gender'], gender_avg['Average'], color='skyblue')
plt.title('Average Grade by Gender')
plt.xlabel('Gender')
plt.ylabel('Average Grade')

plt.subplot(1, 3, 3)
plt.bar(hometown_avg['Hometown'], hometown_avg['Average'], color='lightcoral')
plt.title('Average Grade by Hometown')
plt.xlabel('Hometown')
plt.ylabel('Average Grade')

# Show the plot
plt.show()
```

🌳 Output:

![image](https://github.com/annoyinglyghost/Images-2-/blob/main/pa4%202.png)

## Author
:red_haired_woman: Mariane Iszley V. Samar
- @annoyingltghost—https://github.com/annoyinglyghost
