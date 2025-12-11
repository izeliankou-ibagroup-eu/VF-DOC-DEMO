## Step 1
Log in to your Databricks account.

![](../../assets/databricks-img/1-1.png)

## Step 2
Ensure your Databricks workspace is configured and running as per your requirements.
Get Databricks workspace URL.

Click your workspace name → Manage account

![](../../assets/databricks-img/2a.png)

Click your email address → Workspaces → select URL

![](../../assets/databricks-img/2b-1.png)

## Step 3
Select Authentication type: OAuth or Personal Access Token

### For [OAuth] option:

Generate OAuth secret

Click workspace name → Manage account

![](../../assets/databricks-img/Step-3a-OAuth.png)

User management → Service principals → Click your service principal or create a new one

![](../../assets/databricks-img/Step-3b-OAuth.png)

Click Generate secret

![](../../assets/databricks-img/Step-3c-OAuth-1.png)

### For [Personal Access Token] option:

Generate a Personal access token if you haven’t done already.

Click your user name → Settings

![](../../assets/databricks-img/Step-3a.png)

Developer → Generate new token button

![](../../assets/databricks-img/Step-3b.png)


## Step 4
Ensure you have a volume (whatever volume path you like) where Visual Flow will put prerequisite files. For example:

Click path in your volume → copy button

![](../../assets/databricks-img/4.png)

## Step 5
Click the “+” button to create a new project. In the Create Project window specify: Project Name, Description, Databricks workspace URL, Authentication type (OAuth or Personal access token), Volume path, and click the “Save” button.

“+” select

![](../../assets/databricks-img/Step-5a.png)

**[OAuth]**

![](../../assets/databricks-img/Step-5b-OAuth.png)

**[Personal Access Token]**

![](../../assets/databricks-img/Step-5b-Personal-Access-Token.png)