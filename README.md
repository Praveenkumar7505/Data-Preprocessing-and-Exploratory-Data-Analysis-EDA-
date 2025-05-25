from fpdf import FPDF

# Create a PDF for the theory explanation without any code
class CleanTheoryPDF(FPDF):
    def header(self):
        self.set_font("Arial", "B", 12)
        self.cell(0, 10, "Theory: Data Preprocessing & Exploratory Data Analysis (EDA)", ln=True, align="C")
        self.ln(5)

    def add_section(self, title, content):
        self.set_font("Arial", "B", 14)
        self.multi_cell(0, 10, title)
        self.set_font("Arial", "", 12)
        self.multi_cell(0, 10, content)
        self.ln()

pdf = CleanTheoryPDF()
pdf.set_auto_page_break(auto=True, margin=15)

sections = [
    ("1. Introduction", 
     "This project is a hands-on task where students apply their data science knowledge to clean and explore a real-world dataset. "
     "It is part of a hackathon organized by GUVI and HCL, focusing on Data Preprocessing and Exploratory Data Analysis (EDA).\n\n"
     "Raw data is often incomplete, inconsistent, and unstructured. Preprocessing is essential to convert it into a clean format, and EDA helps uncover insights hidden within the data."),
    
    ("2. Data Preprocessing", 
     "Data preprocessing involves cleaning and preparing the data. It includes:\n"
     "- Handling Missing Values: Filling missing data or removing them.\n"
     "- Feature Selection: Choosing relevant columns.\n"
     "- Feature Engineering: Creating new useful features.\n"
     "- Data Transformation: Scaling or encoding data for consistency."),
    
    ("3. Handling Missing Values and Feature Engineering", 
     "- Missing values can distort analysis results. Common methods include imputation or deletion.\n"
     "- Feature engineering helps in creating more insightful features like extracting time-based components from dates.\n"
     "- These techniques improve model accuracy and the quality of analysis."),
    
    ("4. Exploratory Data Analysis (EDA)", 
     "EDA is used to explore and visualize data to understand its structure and detect patterns.\n\n"
     "- Statistical summaries (mean, median, mode, etc.) help in understanding distributions.\n"
     "- Visualization tools like histograms, scatter plots, and heatmaps reveal insights and trends.\n"
     "- It is essential for identifying relationships and anomalies."),
    
    ("5. Code Quality and Documentation", 
     "Code should be clean, well-commented, and modular. A README file should include:\n"
     "- Project overview\n"
     "- How to run the project\n"
     "- Setup instructions\n\n"
     "GitHub is used for version control and sharing the work."),
    
    ("6. Presentation and Deliverables", 
     "Final submission includes:\n"
     "- A presentation (PDF/PPT) showing your approach and key insights.\n"
     "- A public GitHub repository with all your work.\n\n"
     "Visual clarity and structured explanation are key for a good presentation."),
    
    ("7. Skills You Will Learn & Conclusion", 
     "This project helps develop:\n"
     "- Data preprocessing skills\n"
     "- EDA and visualization techniques\n"
     "- Use of Python libraries like Pandas and Seaborn\n"
     "- Experience with GitHub and communication of insights\n\n"
     "Overall, this project builds your foundation in data analytics and real-world problem solving.")
]

# Add each section to the PDF
for title, content in sections:
    pdf.add_page()
    pdf.add_section(title, content)

# Save the PDF
output_path = "/mnt/data/Theory_EDA_Project_No_Code.pdf"
pdf.output(output_path)

output_path
