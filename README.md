# Deploying a Serverless Web Application on AWS

This guide outlines the steps to deploy a serverless web application on AWS using various services such as S3, Lambda, SQS, DynamoDB, and API Gateway. This application allows you to create, retrieve, update, and delete items through a web interface.

## Prerequisites

Before you begin, ensure that you have the following prerequisites in place:

- An AWS account with the necessary permissions.
- Node.js and npm installed on your local machine.
- Familiarity with AWS services and basic development concepts.

## Deployment Steps

Follow these steps to deploy the serverless web application:

1. **Create a CloudFormation Stack**:
   - Go to the AWS CloudFormation service in the AWS Management Console.
   - Create a new stack using the provided CloudFormation template file.

2. **Stack Visualization**:
   - After creating the stack, view it in the CloudFormation Designer to see a visual representation of the AWS resources being created.

3. **Stack Configuration**:
   - Proceed with the stack creation, providing a name for the stack and following the prompts.

4. **Stack Creation**:
   - Continue with the stack creation process, clicking "Next" as needed, and then create the stack.

5. **Wait for Stack Completion**:
   - Wait for the CloudFormation stack to be completed successfully.

6. **Create an S3 Bucket**:
   - Create an S3 bucket with a unique name.

7. **Enable Static Website Hosting**:
   - In the bucket properties, enable static website hosting and set "index.html" as the index document.

8. **Configure Bucket Permissions**:
   - In the bucket's permissions, disable public access.

9. **Apply Bucket Policy**:
   - Use the provided bucket policy to allow public read access to the bucket.

10. **Edit CORS Configuration**:
    - Modify the CORS (Cross-Origin Resource Sharing) configuration to enable GET requests from other regions.

11. **API Gateway Configuration**:
    - Access the API Gateway created by CloudFormation.

12. **Create a Stage**:
    - Create a stage named "prod."

13. **Create an Integration**:
    - Set up an integration for the Lambda function and make note of the integration ID.

14. **Define Routes**:
    - Create the following routes: GET, PUT, DELETE, and OPTIONS for managing items.

15. **Attach Integrations**:
    - Attach the previously created integration to the routes.

16. **Configure CORS**:
    - Configure CORS settings, allowing access from your S3 bucket URL and other necessary settings.

17. **Deploy CORS**:
    - Deploy the CORS configuration using the "prod" stage.

18. **Get the Invoke URL**:
    - Retrieve the "prod" invoke URL from the API Gateway homepage.

19. **Local Setup**:
    - Download Node.js and npm on your local machine.

20. **Configure the Application**:
    - Modify the `config.ts` file with your API Gateway's ID (letters and numbers from the beginning of your invoke URL).

21. **Build the Application**:
    - In the client folder, run `npm run build` to create a build directory.

22. **Upload to S3**:
    - Upload all files and folders from the build directory to your S3 bucket.

23. **Test the Application**:
    - Access the `index.html` file by pasting the object URL into a browser.

24. **Test Functionality**:
    - Add items from the web page, and they should appear at the bottom.
    - Check the items in DynamoDB via the AWS Management Console.

Congratulations! You have successfully deployed a serverless web application on AWS using various services. Enjoy exploring and using your new application.
