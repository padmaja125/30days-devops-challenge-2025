
# Day 1


The Weather Dashboard is a Python-based application that fetches weather data for multiple cities from the OpenWeather API, formats the data, saves it as JSON files, and uploads the files to an AWS S3 bucket. This project demonstrates how to integrate various services and handle data processing and storage in a cloud environment.

## Features

- Fetches weather data from the OpenWeather API for multiple cities.
- Formats the weather data to include temperature, humidity, conditions, city name, and timestamp.
- Saves the formatted data as JSON files in a local directory.
- Uploads the JSON files to a specified AWS S3 bucket.
- Logs the process and handles errors gracefully.

## Prerequisites
- VS Code/PyCharm installed on your machine
- AWS account with access keys
- OpenWeather API key

## Technical Architecture
 - **Language:** Python 3.x
 - **Cloud Provider:** AWS (S3)
 - **External API:** OpenWeather API
 - **Dependencies:** boto3 (AWS SDK) | python-dotenv| requests

## Setup

### 1.Create the Repository and add Remote Repo to it.

```bash
 git init
 git remote add origin yourRepo.git
 cd yourRepo
```

### 2. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set Up Environment Variables

Create a `.env` file in the root directory of the project and add the following environment variables:

```properties
OPENWEATHER_API_KEY=your_openweather_api_key
AWS_ACCESS_KEY=your_aws_access_key
AWS_SECRET_KEY=your_aws_secret_key
AWS_REGION=your_aws_region
S3_BUCKET_NAME=your_s3_bucket_name
```

Replace the placeholders with your actual API key and AWS credentials.

### 5. Add `.env` to 

.gitignore



Ensure that your `.env` file is not tracked by Git to keep your credentials secure. Add the following line to your 

.gitignore

 file:

```plaintext
.env
__pycache__/
.zip
env
```

## Usage

### Running the Script

Activate the virtual environment if not already activated:

```bash
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

Run the script:

```bash
python src/weather_data_extract.py
```

### Enter Cities

When prompted, enter the cities separated by commas. For example:

```plaintext
Enter cities separated by commas: London, Abuja, Kent, Toronto, Tokyo, Japan, New York, Dubai, Berlin, Washington DC, Beijing
```

The script will fetch the weather data for each city, format it, save it as JSON files in the `data/` folder, and upload the files to the specified S3 bucket.

### Logs

The script logs the process and any errors encountered. The logs are printed to the console and include timestamps, log levels, and messages.

### Data Extracted from Open API and fetching to the local and loading to S3
![Alt text](FetchingFromAPI.png?raw=true "Data Extracted from Open API and fetching to the local and loading to S3")
### S3 bucket created
![Alt text](S3BucketCreated.png?raw=true "S3 bucket created")
### files uploaded to s3 bucket
![Alt text](dataInS3.png?raw=true "files uploaded to s3 bucket")

## Resources
- [Docker Installation Guide](https://docs.docker.com/get-started/get-docker/): Follow this guide to install Docker on your machine.
- [OpenWeather API Documentation](https://openweathermap.org/api): Learn more about the OpenWeather API.
- [AWS S3 Documentation](https://docs.aws.amazon.com/s3/): Comprehensive guide to using AWS S3.
- [AWS CLI Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html): Guide to configuring the AWS CLI.
- [Medium Post](https://medium.com/@padhu.ramsh/devops-30days-challenge-eaa8e9d7c22c): DevOps 30days Challenge

## License
This project is licensed under the MIT License.
