1. Create a Common Header Component Repository:

Start by creating a separate Git repository for your common header component. Initialize a new repository or use an existing one. Commit your header component code to this repository.

# Create a new directory for the common header component

mkdir common-header-component
cd common-header-component

# Initialize a new Git repository

git init

# Add, commit, and push your header component code

git add .
git commit -m "Initial commit"
git remote add origin <common-header-repo-url>
git push -u origin master

2. Add the Submodule to Your React Applications:

For each of your React applications, you can add the common header component repository as a submodule.

# Navigate to your React application's src directory

cd path/to/your/react-app/src

# Add the common header component as a submodule

git submodule add <common-header-repo-url> common-header

# Commit the changes to your application's repository

git add .
git commit -m "Added common header component as submodule"
git push

Make sure to replace <common-header-repo-url> with the actual URL of your common header component repository.

3. Initialize and Update Submodules:

When you clone your application's repository or if you've just added a submodule, you need to initialize and update the submodules.

# Initialize submodules

git submodule init

# Update submodules to fetch the code from the common header component repository

git submodule update --recursive

4. Usage in Your React Application:

You can import and use the common header component within your React application as if it were a local component. For example:

import CommonHeader from './common-header';

function App() {
return (
<div>
<CommonHeader />
{/_ Your application content _/}
</div>
);
}

5. Updating the Common Header Component:

If you need to make changes to the common header component, navigate to the common-header directory within your React application and treat it as a separate Git repository. You can make your changes, commit them, and push them to the common header component repository. Then, in your React applications, you can update the submodules to pull in the latest changes.

# Inside the common-header directory in your React application

cd common-header

# Make changes and commit them

git add .
git commit -m "Updated common header component"
git push

# In your React application, update the submodule to get the latest changes

git submodule update --remote

Using Git submodules provides a way to share a common component across multiple projects while maintaining version control. However, keep in mind that it introduces some complexity, and you need to ensure that the submodule repositories are accessible and up to date for all your team members.
