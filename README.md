# Belly Button Biodiversity

This project is an interactive dashboard that visualizes the Belly Button Biodiversity dataset. The dataset catalogs the microbes that colonize human navels. The dashboard allows users to explore the top 10 Operational Taxonomic Units (OTUs) found in each sample and view detailed demographic information for each individual.

## Project Overview

- **Data Source:** The dataset is read in using the D3 library from the URL [samples.json](https://static.bc-edx.com/data/dla-1-2/m14/lms/starter/samples.json).
- **Technology Stack:** HTML, CSS, JavaScript, D3.js, Plotly.js.

## Features

1. **Interactive Bar Chart**: A horizontal bar chart displays the top 10 OTUs found in each individual sample. 
   - **Data Used**:
     - `sample_values` are used for the bar chart values (length of bars).
     - `otu_ids` are used for the bar chart labels (y-axis).
     - `otu_labels` are used as hovertext for the chart.
   - **Implementation**: The bar chart updates based on the selected sample from a dropdown menu.

2. **Bubble Chart**: A bubble chart displays each sample’s OTU data.
   - **Data Used**:
     - `otu_ids` for the x-axis values.
     - `sample_values` for the y-axis values and marker sizes.
     - `otu_ids` for marker colors.
     - `otu_labels` for text values (hovertext).
   - **Implementation**: The bubble chart provides a visual representation of the OTU frequency and variety in each sample.

3. **Demographic Information Display**: The dashboard displays each sample's metadata, such as demographic information.
   - **Data Used**: The `metadata` JSON object contains details such as `id`, `ethnicity`, `gender`, `age`, `location`, `bbtype`, and `wfreq`.
   - **Implementation**: A loop goes through each key-value pair from the metadata JSON object and appends it to the `#sample-metadata` panel.

4. **Dynamic Updates**: All plots and demographic information update dynamically when a new sample is selected from the dropdown menu.

5. **Console Logging**: Used `console.log()` at various points to track data flow and inspect the data structure.
How to View the Logs:
  - Open Developer Tools
  - Press F12 in your browser to open the Developer Tools.
  - Go to the "Console" tab.
  - Interact with the Dashboard:
    - As interacting with the dropdown menu and the dashboard, the console.log outputs can be seen appearing in the console.
    - These logs will show the data at each key step of the code execution, helping to verify that everything is working as expected.
    - Using console.log in these locations will give us detailed insight into how the data is being processed and will help us quickly identify any issues or unexpected behaviors.

6. **Deployment**: The app is deployed using GitHub Pages, making it accessible as a static web page.
   - Go to Settings in GitHub page
   - At the section "Code and Automation", click into the "Pages"
   ![image](https://github.com/user-attachments/assets/506798e6-1d0b-46e9-a966-c6734de5670e)
   - Build the main branch into the GitHub page
   - The live website can be deployed at [Belly Button Biodiversity Dashboard](https://ichbinfreya.github.io/belly-button-challenge/)

## How to Access the Web

To run the project locally, git clone the repo:

1. Open the Project in Visual Studio Code
3. Navigate to the project folder in VS Code.
4. Launch with Live Server:
   - Use the Live Server extension in VS Code to view the project.
   - Right-click on index.html and select "Open with Live Server."
5. View in Browser: Once Live Server is running, open the web browser and navigate to: http://127.0.0.1:5500/index.html

## Code Explaination

1. **Loading the Data**: Data is loaded using D3's `d3.json()` method from the provided JSON URL
   
2. **Building Charts**:
  - Bar Chart: Plots the top 10 OTUs for the selected sample.
    - `sample_values`, `otu_ids`, and `otu_labels` are sliced and reversed to create a descending order bar chart.
  - Bubble Chart: Displays all OTUs for the selected sample.
    - Uses `otu_ids` for the x-axis, sample_values for the y-axis and marker size, and `otu_labels` for hovertext.
    
3. **Displaying Metadata**: The demographic information is displayed using the buildMetadata function, which filters and appends relevant data to the #sample-metadata panel.
  
4. **Dynamic Updates**: The `optionChanged()` function is triggered when a new sample is selected, calling `buildCharts()` and `buildMetadata()` to update the visuals.
