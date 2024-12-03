# **Blog Application - MongoDB Schema**

You are tasked with designing a comprehensive data model for a blog application using MongoDB. This application will support user-generated content, such as blog posts, comments, and user interactions like likes. The schema should ensure data consistency, enforce validation rules, and support efficient queries for essential functionalities. Below are the detailed requirements for the schema.

create and schema.js file and write the schema in that file.

# **Requirements**

## 1. Blog Posts

Each blog post will contain the following fields:

- **Title**: A required string that serves as the title of the post. This field must be unique and have a minimum length of 5 characters to ensure meaningful titles.
- **Content**: A required string that holds the main content of the post. To maintain quality, this field must have a minimum length of 50 characters.
- **Author**: A reference to a document in the User collection, representing the user who created the post.
- **Tags**: An array of strings to store tags or keywords associated with the post, such as `['technology', 'programming', 'tutorial']`.
- **Category**: A string representing the category of the post. If not provided, it should default to `"General"`.
- **Published**: A boolean field indicating whether the post is published. By default, this value should be `false`.
- **Created At**: A date field automatically set to the current date and time when the post is created.
- **Updated At**: A date field that automatically updates whenever the post is modified, ensuring accurate tracking of changes.

## 2. Comments

Each blog post can have multiple comments. The comments field should store an array of subdocuments, with each subdocument containing the following:

- **User**: A reference to the User collection, representing the user who made the comment.
- **Message**: A required string containing the comment text.
- **Commented At**: A date field automatically set to the current date and time when the comment is created.

## 3. Likes

Each blog post should include a **likes** field to store an array of user IDs. This field keeps track of which users liked the post, enabling features like displaying the number of likes or checking if a specific user liked a post.

## 4. Validation Rules

To ensure data integrity, implement the following validation rules:

- The **title** must be unique and at least 5 characters long.
- The **content** must have a minimum length of 50 characters.

## Additional Notes

- The **author** and **user** fields for blog posts and comments, respectively, should reference the `_id` field of the User collection.
- Use **timestamps** (`createdAt` and `updatedAt`) to enable sorting and filtering posts by creation or modification time.
- Ensure **indexes** are created on the **title** and **tags** fields for efficient querying.

## Deliverable

Using JavaScript syntax, write the MongoDB schema for the BlogPost collection. Ensure it meets the above requirements and includes:

- All specified fields and their types.
- Default values where applicable.
- Validation rules for title and content.
- Relationships with the User collection for **author** and **comments.user**.

# **How to Fork and Set Up Your Repository**

---

## **1. Fork the Repository on StackBlitz**

- You will be provided with a **StackBlitz** link for the assignment.
- Open the link in your browser and click on the **Fork** button in StackBlitz.  
  This will create a copy of the repository in your StackBlitz account.

---

## **2. Clone the Repository to Your Personal GitHub**

- After forking, you can download the project or push it directly to your personal GitHub repository:
  - **Option 1: Download and Push**
    1. Download the repository files from StackBlitz.
    2. Open your terminal/command prompt, navigate to the project folder, and run:
       ```bash
       git init
       git remote add origin <your_github_repo_url>
       ```
       Replace `<your_github_repo_url>` with your personal GitHub repository URL.
    3. Commit and push the files to your GitHub repository:
       ```bash
       git add .
       git commit -m "Completed the assignment"
       git push -u origin main
       ```
  - **Option 2: Push Directly**
    1. Use the **Push to GitHub** option in StackBlitz to directly connect and push the repository to your GitHub account.

---

## **3. Submission Instructions**

- Once your code is successfully pushed to GitHub:
  1. Copy the link to your GitHub repository.
  2. Submit the link on the assignment submission portal.  
     The link should follow this format:  
     **`https://github.com/<your_username>/<repository_name>`**

---

### **Example Submission**

If your GitHub username is `johnDoe` and the repository name is `assignment-repo`, the submission link would look like this:  
**`https://github.com/johnDoe/assignment-repo`**
