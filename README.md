# gitlab-n8n-CrowdStrike
This repo serves as a solid example of leveraging n8n to circumvent licensing limitations while maintaining log integrity across multiple GitLab endpoints.
This workflow is currently for CrowdStrike (using the AWS S3 Data Connector); further developments will be made to support other SIEM platforms

Steps:
1. Set Trigger Node.

2. HTTP Event Nodes - 14 different nodes in this instance (Defining API endpoints/Header Auth (Tokens), and pagination parameters).

3. Edit Field Node (Did manual mapping for fields that would be relevant to this case).

4. Merge Node (To prevent the creation of different workflows for each HTTP node).

5. Code Node (CrowdStrike requires amount parsing using CPS; this can be defined in the metadata section of the code.
   Also, rename the logs and convert them to binary to make it readable for the SIEM.

5. S3 Node (Defining relevant fields like bucket name, account details, etc).
