sudo apt update && sudo apt upgrade -y

# Add the NodeSource repository for Node.js:
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
# Replace 18.x with your desired Node.js version:
# For the latest LTS version: setup_18.x
# For the latest current version: setup_20.x

# Install Node.js:
sudo apt install -y nodejs
# Verify the installation:
node -v
npm -v

# Install PM2 globally:
sudo npm install pm2@latest -g
# Verify the installation:
pm2 --version

git clone https://github.com/mahadihassanrazib/full-stack-crud-project-with-react-node-mysql.git

# Navigate to the project directory:
cd full-stack-crud-project-with-react-node-mysql

# Navigate to the backend directory:
cd server

# Install dependencies:
npm install

# Create and edit the .env file:
cp .env.example .env

sudo nano .env

# Update the following environment variables according to your MySQL database configuration:
DB_HOST=
DB_USER=
DB_PASSWORD=
DB_DATABASE=

# Save and exit (`Ctrl + X`, then `Y`, then `Enter`).

# Start the backend server using PM2:
pm2 start index.js --name api-server --watch --env PORT=3000

# To view status:
pm2 status

# To view logs:
pm2 log api-server
