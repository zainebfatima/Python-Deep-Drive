🐍 Python Deep Dive — Lab 35

🎨 Quick Data Visualization with Matplotlib

<blockquote>
  *Learning Goal:* Turn raw numbers into meaningful visual information using Python.
</blockquote>🎯 Objectives

- Understand the basics of data visualization.
- Install and configure Matplotlib.
- Create line graphs, bar charts, pie charts and histograms.
- Understand the benefits of quick data visualization.
- Learn how to save graphs as image files.

---

🟢 1. What is Data Visualization?

Data visualization means representing information through visual elements such as graphs and charts instead of displaying only raw numbers.

Why is it useful?

- Makes complex data easier to understand.
- Helps identify patterns and trends.
- Makes comparisons quicker.
- Helps communicate information effectively.
- Supports better decision-making.

🔵 2. Introduction to Matplotlib

Matplotlib is a Python library used to create graphs, charts and other visual representations of data.

We imported its plotting module using:

import matplotlib.pyplot as plt

Here, "plt" is an alias that makes it easier to use Matplotlib functions.

⚙️ Installation and Setup

Working in the Al-Nafi Ubuntu cloud environment:

python3 -m venv lab35_env
source lab35_env/bin/activate

Install pip if it is not available in the environment:

python3 -m ensurepip --upgrade

Install Matplotlib:

python3 -m pip install matplotlib

Verify installation:

python3 -c "import matplotlib; print(matplotlib._version_)"

---

📈 3. Line Graph

Purpose: A line graph helps visualize changes and trends over time.

Code

import matplotlib.pyplot as plt

days = ["Mon", "Tue", "Wed", "Thu", "Fri"]
sales = [10, 20, 15, 30, 25]

plt.plot(days, sales, color="royalblue", marker="o")

plt.title("Weekly Sales")
plt.xlabel("Days")
plt.ylabel("Sales")

plt.savefig("weekly_sales_line.png")

Understanding the code

Function| Purpose
"plt.plot()"| Creates a line graph
"color"| Changes the line colour
"marker"| Adds markers to data points
"plt.title()"| Adds a graph title
"plt.xlabel()"| Labels the horizontal axis
"plt.ylabel()"| Labels the vertical axis

Observation: The line moves upward when sales increase and downward when sales decrease.

---

🟠 4. Bar Chart

Purpose: A bar chart helps compare values between different categories.

Code

import matplotlib.pyplot as plt

days = ["Mon", "Tue", "Wed", "Thu", "Fri"]
sales = [10, 20, 15, 30, 25]

plt.bar(
    days,
    sales,
    color=["red", "orange", "gold", "green", "royalblue"]
)

plt.title("Weekly Sales Comparison")
plt.xlabel("Days")
plt.ylabel("Sales")

plt.savefig("weekly_sales_bar.png")

Observation: Each bar represents a value. A taller bar indicates a higher value.

---

🟣 5. Pie Chart

Purpose: A pie chart shows how individual values contribute to a whole.

Code

import matplotlib.pyplot as plt

products = ["Laptop", "Tablet", "Phone A", "Phone B", "Phone C"]
sales = [10, 20, 15, 30, 25]

plt.pie(
    sales,
    labels=products,
    autopct="%1.1f%%",
    colors=["purple", "skyblue", "gold", "pink", "lightgreen"]
)

plt.title("Product Sales Distribution")

plt.savefig("weekly_sales_pie.png")

Understanding a new argument

"autopct="%1.1f%%"" displays percentages on the pie chart.

For example:

- Laptop: 10%
- Tablet: 20%
- Phone A: 15%
- Phone B: 30%
- Phone C: 25%

Observation: The size of each slice represents its contribution to the total.

---

🔴 6. Histogram

Purpose: A histogram shows the distribution of numerical data by grouping values into intervals.

Code

import matplotlib.pyplot as plt

scores = [45, 50, 55, 60, 65, 70, 75, 80, 85, 90]

plt.hist(
    scores,
    bins=5,
    color="mediumseagreen",
    edgecolor="black"
)

plt.title("Students Test Scores")
plt.xlabel("Scores")
plt.ylabel("Number of Students")

plt.savefig("students_histogram.png")

Understanding the code

- "plt.hist()" creates a histogram.
- "bins=5" divides the data range into five intervals.
- "edgecolor="black"" adds borders around the bars.

Observation: The height of each bar represents how many values fall within that interval.

---

📂 7. Saving Graphs as Images

In a cloud terminal, "plt.show()" may not display graphs because the environment might not support interactive graphical windows.

We used:

plt.savefig("weekly_sales.png")

This saves the graph as a PNG image.

To view it:

xdg-open weekly_sales.png

Important file-management lesson

- Same filename and location = existing image is replaced.
- Different filename = a new image is created.
- Changing Python code does not automatically delete previously saved images.

To check saved files:

ls -lh *.png

---

🧠 8. Troubleshooting and Lessons Learned

Error 1: pip command not found

Problem: The terminal could not find the "pip" command.

Solution: Set up pip in the virtual environment and use:

python3 -m pip install matplotlib

Error 2: SyntaxError — '(' was never closed

Problem: A closing parenthesis was missing from the "plt.pie()" statement.

Incorrect:

plt.pie(sales, labels=products, autopct="%1.1f%%"

Correct:

plt.pie(sales, labels=products, autopct="%1.1f%%")

Lesson: Every opening parenthesis must have a matching closing parenthesis.

Error 3: FigureCanvasAgg is non-interactive

Problem: The cloud terminal could not display the graph through "plt.show()".

Solution: Save the graph instead:

plt.savefig("graph.png")

Then open it with:

xdg-open graph.png

---

🔐 9. Cybersecurity Applications

Data visualization is useful in cybersecurity because security analysts often work with large amounts of numerical data.

Examples:

- Line graphs: Monitor failed login attempts over time.
- Bar charts: Compare security alerts across different systems.
- Pie charts: Visualize the distribution of different alert categories.
- Histograms: Understand the distribution of network traffic measurements.

Visualization can help analysts identify unusual patterns that deserve further investigation.

---

📚 10. Quick Revision

Visualization| Function| Main Purpose
📈 Line Graph| "plt.plot()"| Trends and changes
📊 Bar Chart| "plt.bar()"| Comparing categories
🥧 Pie Chart| "plt.pie()"| Parts of a whole
📉 Histogram| "plt.hist()"| Numerical distribution

⭐ Key Takeaways

1. Matplotlib is a Python data visualization library.
2. "matplotlib.pyplot" provides plotting functions.
3. Graphs make data easier to understand.
4. "plt.savefig()" saves graphs as image files.
5. Different visualizations serve different purposes.
6. Virtual environments help manage project dependencies.

---

🏆 Lab 35 Completion

Status: Practical work completed!

What I accomplished:

- Installed Matplotlib in an Ubuntu virtual environment.
- Created four types of visualizations.
- Saved and viewed PNG graph files.
- Fixed a syntax error independently with guidance.
- Understood how filenames affect saved images.
- Explored practical uses of visualization in cybersecurity.

Biggest Lesson: Programming becomes much more interesting when you can turn your code into something you can actually see!

Python Deep Dive — Keep Learning, Keep Building. 
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8ee6e149-7b1d-4302-8388-14d8d361dd6d" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/22032760-a596-4522-bbc7-1eb8a3c0e214" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/544da1e3-0336-43b4-907d-98def493ecec" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1a568d29-9d21-4a8f-9fcf-141f1d944595" />



