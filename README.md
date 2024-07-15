Here's a basic template for your README file based on the information you provided:

---

# Bangalore Home Prices Prediction Website

This project series walks through the process of building a real estate price prediction website for Bangalore homes. It covers everything from data cleaning and model building to deploying the application on AWS EC2 using Nginx for server configuration.

## Project Components

1. **Data Science Model**
   - Built using Python, Numpy, Pandas, Matplotlib, and Scikit-learn.
   - Includes data cleaning, outlier detection, feature engineering, and dimensionality reduction.
   - Utilizes linear regression with GridSearchCV for hyperparameter tuning.

2. **Python Flask Server**
   - Serves the trained model to handle HTTP requests.
   - Uses Flask for creating APIs to predict home prices based on user inputs.

3. **Web Application**
   - Developed in HTML, CSS, and JavaScript.
   - Allows users to input home features (square footage, number of bedrooms, etc.).
   - Communicates with the Flask server to retrieve predicted prices.

4. **Deployment on AWS EC2**
   - Creates an EC2 instance (Linux-based).
   - Uses SSH for secure communication and FileZilla for file transfer.
   - Configures Nginx as a reverse proxy server for handling web requests.

## Deployment Steps

### Setting Up AWS EC2 Instance

1. Create an EC2 instance with a free-tier Linux OS.
2. Generate and save SSH key-pair for secure access.
3. Connect to EC2 instance using SSH:
   ```
   ssh -i "bhp.pem" ubuntu@ec2-<your-instance-ip>.compute.amazonaws.com
   ```

### Installing and Configuring Nginx

1. Update and install Nginx:
   ```
   sudo apt-get update
   sudo apt-get install nginx
   ```

2. Configure Nginx:
   - Remove default page and symlink.
   - Create a new configuration file (`bhp.conf`) in `/etc/nginx/sites-available`.
   - Enable the configuration by creating a symlink in `/etc/nginx/sites-enabled`.
   - Restart Nginx:
     ```
     sudo service nginx restart
     ```

### Deploying the Flask Application

1. Install Python and dependencies on the EC2 instance.
2. Transfer project files to EC2 using FileZilla.
3. Install required Python packages:
   ```
   pip install -r requirements.txt
   ```

4. Run the Flask server:
   ```
   python3 server.py
   ```

## Additional Basic Linux Commands 

- `less`: View file contents.
- `ll`: List files with detailed information.
- `ln -s`: Create symbolic links.
- Basic file navigation (`cd`, `ls`).

