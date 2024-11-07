# SwaggerPetStoreAPICollection
 
This repository contains a GitHub Actions workflow that automates the execution of the **Swagger PetStore API** collection using [Newman](https://github.com/postmanlabs/newman), which runs Postman collections from the command line. The workflow generates an HTML report of the test results.
 
## Workflow Overview
 
The workflow is defined in the `.github/workflows/SwaggerPetStoreAPICollection.yml` file. It is triggered on:
 
- **Push** events on the `main` branch
- **Pull requests** to the `main` branch
- **Manual runs** from the Actions tab on GitHub
 
### Workflow Steps
 
1. **Checkout Repository**: Checks out the repository to allow the workflow to access files.
 
2. **Create Directory**: Creates a directory called `HtmlReport` to store the generated report.
 
3. **Set up Node.js**: Installs Node.js 17.x to ensure compatibility with Newman.
 
4. **Install Dependencies**:
   - Installs Newman globally for running the collection.
   - Installs the `htmlextra` reporter to generate a detailed HTML report.
 
5. **Run Collection**: Executes the Postman collection (`01 - Swagger Petstore.postman_collection.json`) and generates an HTML report in the `HtmlReport` directory.
 
6. **Publish Report**: Uploads the HTML report as an artifact named `Reports` for download from the Actions run page.
 
## Running the Workflow Manually
 
To run this workflow manually:
 
1. Navigate to the **Actions** tab in your GitHub repository.
2. Select the `SwaggerPetStoreAPICollection` workflow.
3. Click **Run workflow** and confirm the branch.
 
## Viewing the Report
 
After the workflow completes, the HTML report can be downloaded as an artifact:
 
1. Go to the **Actions** tab in your repository.
2. Open the latest workflow run.
3. Find the **Reports** artifact in the **Artifacts** section and download it.
4. Open `report.html` in a web browser to view the test results.
 
## Prerequisites
 
Ensure that the collection file (`01 - Swagger Petstore.postman_collection.json`) is present in the root of the repository.
 
## Dependencies
 
- **Node.js**: Version 17.x
- **Newman**: For running the Postman collection
- **Newman Reporter (htmlextra)**: For generating HTML reports with enhanced detail
