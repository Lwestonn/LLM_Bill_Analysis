Bill Analysis Tool
This Python notebook processes PDF files of California bills and creates a CSV summary using Google's Gemini API.

How to run:
- Google Colab or Jupyter notebook
- Google AI Studio API key
- Folder of PDF bill files

Setup:
1. Get a Google AI Studio API key from https://aistudio.google.com
2. Put your PDF files in a folder
3. Set these environment variables:
	GOOGLE_API_KEY - your API key
	PDF_FOLDER - path to your PDF folder
You can set them in the notebook like this:
- os.environ['GOOGLE_API_KEY'] = 'your-key-here'
- os.environ['PDF_FOLDER'] = '/path/to/pdfs'

Then just run all the cells.

Output: 
Creates a CSV file called bill_summary.csv with these columns:
- Bill number
- Sponsors/Co-sponsors
- Short bill summary (3-5 sentences)
- Topics and Keywords
- Relevant Team Names

How it works:
The notebook reads each PDF, extracts the text, then uses the Gemini API to:
- Find bill numbers and sponsors
- Write summaries
- Extract keywords
- Match bills to Office of Innovation teams

Teams it matches to:
- Data + Policy - data analysis, dashboards, AI policy, digital services, technology policy
- Direct File - state tax filing, IRS Direct File program, Treasury department
- Doula Medicaid Enrollment - doula care, Medicaid coverage, managed care organizations
- Food Security - nutrition benefits, SNAP, school lunch programs, EBT, USDA programs

Notes:
- The notebook uses pdfplumber to read PDFs and requests to call the Gemini API
- All the analysis is done by the LLM, not hardcoded rules
- Output CSV goes in the same folder as your PDFs
- Should work with different bill formats (AB, SB, etc.)
