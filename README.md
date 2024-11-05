# Deploy JSON Server on Vercel

This repository contains a simple setup for deploying a `json-server` instance to Vercel. `json-server` provides a full fake REST API with zero coding, and by deploying it to Vercel, you can have a quick and scalable API solution.

## Prerequisites

1. **Node.js**: Ensure you have Node.js installed (preferably the latest stable version).
2. **Vercel Account**: Sign up at [vercel](vercel.com) and install the `Vercel CLI` if desired.

## Project Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/mahdi-q/Deploy-JSON-Server-On-Vercel.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Movie-Character-App-Project
   ```
3. Install the dependencies:
   ```bash
   npm install
   ```

## Project Structure

- `api/server.js`: This file contains the json-server setup and routes configuration.
- `vercel.json`: Configuration file for Vercel to customize deployment settings.

## Key Files

- `api/server.js`:
  - Configures json-server to use an in-memory database.
  - Sets up routing and middleware for a simple JSON API.
- `vercel.json`:
  - Directs Vercel to deploy server.js as a serverless function.
  - Sets up rewrites to make the server accessible via the root URL.

## Vercel Deployment

1. **Push to GitHub**: Push your project to GitHub if it’s not there already.

2. **Link with Vercel**:

   - Go to your Vercel dashboard.
   - Select New Project and import your GitHub repository.
   - In the project settings, Vercel should automatically detect the vercel.json configuration.

3. **Deploy**:
   - Vercel will deploy the project using the configurations specified.
   - After deployment, you should see your JSON server running at https://deploy-json-server-on-vercel-template.vercel.app.

## Example Requests

Once deployed, you can use the following example requests:

- GET `/posts`: Fetches all posts.
- POST `/posts`: Creates a new post.
- PUT `/posts/:id`: Updates an existing post.
- DELETE `/posts/:id`: Deletes a post.

## Sample Database (Embedded)

The `api/server.js` file contains an embedded sample database to avoid file system issues on Vercel. You can update this database to suit your application needs.

Example in-memory data structure:

```bash
const db = {
  posts: [
    { id: "1", title: "a title", views: 100 },
    { id: "2", title: "another title", views: 200 },
  ],
  comments: [
    { id: "1", text: "a comment about post 1", postId: "1" },
    { id: "2", text: "another comment about post 1", postId: "1" },
  ],
  profile: {
    name: "typicode",
  },
};
```

## Additional Notes

- This configuration uses `json-server` with an in-memory database, which resets on each deployment or server restart.

## Refrences & Tools

- https://github.com/typicode/json-server
- https://vercel.com/docs
- https://chatgpt.com
