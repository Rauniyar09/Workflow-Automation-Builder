# Workflow-Automation-Builder

 
# Instructions to run the project locally.(react.js)
 
 To run this project locally, you’ll need to have the following installed:

Node.js (version 16 or higher)
npm (Node Package Manager) or yarn
npm install or yarn install
npm start or yarn start to run the application

Once the development server starts, navigate to http://localhost:3000 in your browser to view the project.



# Design Decisions and Trade-offs
React and React Flow:

Reasoning: React was chosen for its component-based architecture, which helps in breaking down complex workflows into manageable pieces. React Flow is used to visualize workflows and manage nodes and edges in an interactive canvas.
Trade-offs: React Flow is a specialized library that introduces additional complexity compared to simple DOM manipulation. However, it simplifies the creation of flowcharts and makes it easier to manage workflows visually.
State Management:

Reasoning: The application uses a custom store via the useWorkflowStore hook to manage the state of nodes, edges, and workflow data. This helps maintain a centralized state, which can be accessed across components without prop drilling.
Trade-offs: Using a global store for state management can make the code more difficult to test and maintain if it grows too large, but in this case, it's necessary for efficient state updates across multiple components.
Form Handling:

Reasoning: React Hook Form was used to handle form submission and validation in the NodeForm component. It provides a simple API for managing form state and avoids unnecessary re-renders.
Trade-offs: While React Hook Form minimizes re-renders, it might require some learning curve for new developers unfamiliar with its API.
CSS vs. Tailwind:

Reasoning: Initially, Tailwind CSS was used for styling due to its utility-first approach, making it quick to style components directly in JSX. However, for this version, regular CSS was chosen for simplicity and better organization.
Trade-offs: Tailwind allows for fast styling but can lead to messy code with many utility classes. Regular CSS provides more maintainable, reusable styles but might require more time upfront.



# Assumptions

Node IDs are unique: It is assumed that each node has a unique id that is used for identifying nodes for deletion or updates.

JSON Import and Export: The application supports importing and exporting workflow data in JSON format. The structure of the JSON data is assumed to match the format expected by the app (e.g., nodes and edges in the correct format).

Node Content Editing: The project assumes that only basic text input for nodes (such as task names) is required, with no complex content editing needed.

Browser Compatibility: The project is assumed to be used in modern browsers like Chrome, Firefox, and Edge. Compatibility with older browsers like Internet Explorer is not guaranteed.

State is Managed Locally for Simplicity: In this project, state management is handled using the custom store via hooks (useWorkflowStore), which is suited for smaller applications. For larger applications, a more robust state management system like Redux could be considered.
