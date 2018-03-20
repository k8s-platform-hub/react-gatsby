# Step 1: Pulls a simple ubuntu image with node 8 installed in it
FROM node:8

# Step 2: Create a directory called "app"
RUN mkdir app

# Step 3: Copy the package.json file from the local machine to the app directory inside the container
COPY app/package.json app/

# Step 4: Run npm install to install dependencies
RUN cd app && npm install

# Step 5: Add all source code into the app directory from your local app directory
ADD app app/

# Step 6: Set app as our current work directory
WORKDIR app

# Step 7: Create an optimised build for production
RUN npm run build

# Step 8: Run npm run start -- -p 8080 to run the app at port 8080
CMD ["npm", "run", "start", "--", "-p", "8080"]
