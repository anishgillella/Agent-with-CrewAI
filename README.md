# Healthcare Diagnosis and Treatment Recommendations

This repository contains a Streamlit application that provides healthcare diagnosis and treatment recommendations based on user input. It utilizes CrewAI agents for diagnosing medical conditions and recommending treatment plans.

## Features

- Collect user input for gender, age, symptoms, and medical history.
- Use CrewAI agents for medical diagnosis and treatment recommendations.
- Integrate tools for web scraping and search.
- Generate a downloadable Word document with the diagnosis and treatment plan.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/anishgillella/healthcare-diagnosis-recommendations.git
    cd healthcare-diagnosis-recommendations
    ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Create a `.env` file in the root directory and add your API keys:
    ```plaintext
    OPENAI_API_KEY=your_openai_api_key
    SERPER_API_KEY=your_serper_api_key
    ```

## Usage

1. Run the Streamlit application:
    ```bash
    streamlit run app.py
    ```

2. Open the application in your web browser:
    ```plaintext
    http://localhost:8501
    ```

3. Enter the required information (gender, age, symptoms, medical history) and click "Get Diagnosis and Treatment Plan". The application will generate and display the recommendations. You can also download the recommendations as a Word document.

## Data Ingestion

- **User Input**: Collect user data through Streamlit input fields (gender, age, symptoms, medical history).
  ```python
  gender = st.selectbox("Gender", ["Male", "Female", "Other"])
  age = st.number_input("Enter Age", min_value=0, max_value=120, value=25)
  symptons = st.text_area("Enter Symptoms")
  medical_history = st.text_area("Enter Medical History")
  ```

- **Web Scraping**: Use `ScrapeWebsiteTool` for web scraping.
  ```python
  from crewai_tools import ScrapeWebsiteTool
  scrape_tool = ScrapeWebsiteTool()
  ```

- **Search**: Use `SerperDevTool` for search operations.
  ```python
  from crewai_tools import SerperDevTool
  search_tool = SerperDevTool()
  ```

## Code Overview

- `app.py`: The main file containing the Streamlit application logic.
- The application initializes various CrewAI components, sets up agents for diagnosis and treatment recommendations, and processes user input to generate and display results.

## Dependencies

- `streamlit`
- `crewai`
- `langchain_openai`
- `python-dotenv`
- `docx`

Make sure to install all dependencies listed in the `requirements.txt` file.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgements

- [CrewAI](https://github.com/crewai)
- [Streamlit](https://streamlit.io/)
- [OpenAI](https://openai.com/)

Feel free to contribute to this project by submitting issues or pull requests.
