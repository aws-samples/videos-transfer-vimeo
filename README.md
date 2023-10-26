# videos-transfer-vimeo
[![en](https://img.shields.io/badge/lang-pt--br-green.svg)](https://github.com/aws-samples/videos-transfer-vimeo/edit/main/README.pt-br.md)

This project demonstrates how to transfer videos from a Vimeo account to an Amazon S3 bucket.

## Prerequisites

- [Python 3](https://www.python.org/downloads/), installed
- A [Vimeo](https://vimeo.com/) account with a Standard plan or higher
- A bucket in Amazon S3
## Step-by-Step

1. Install the necessary libraries using [pip](https://pypi.org/project/pip/): ``` pip install -r requirements.txt``` or ``` pip3 install -r requirements.txt```
2. In the same directory as the python script, create a file called ```.env```, with the following format, and fill in the necessary fields:
 ``` 
 AWS_ACCESS_KEY = ''
 AWS_SECRET_ACCESS_KEY = ''
 BUCKET_NAME = ''
 VIMEO_CLIENT_IDENTIFIER = ''
 VIMEO_TOKEN = ''
 VIMEO_CLIENT_SECRET =   ''
 OPTIONAL_PATH = ''
```
- ```AWS_ACCESS_KEY``` and ```AWS_SECRET_ACCESS_KEY```: the public and private keys, respectively, of a user with permissions on the bucket
  - The required [permission](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_id-based) is ```s3:PutObject``` on the bucket (```arn:aws:s3:::<bucket-name>/*```)
- ```BUCKET_NAME```: the name of the bucket
- ```VIMEO_CLIENT_IDENTIFIER```:
   - Go to [https://developer.vimeo.com/apps](https://developer.vimeo.com/apps)
   - Create an App, filling in its name and description
   - Copy the value in ```Client identifier``` to the variable
- ```VIMEO_TOKEN``` and ```VIMEO_CLIENT_SECRET```:
   - On the same page, under ```Authentication```, select the field ```Authenticated (you) ```
   - Select the ```Public```, ```Private``` and ```Video Files``` scopes
   - Click on ```Generate```
   - In the ```Personal Access Tokens``` tab, copy the value in ```Token``` to the variable ```VIMEO_TOKEN```
   - In the ```Manage App Secrets``` tab, copy the value in ```Client secrets``` to the variable ```VIMEO_CLIENT_SECRET```
- ```OPTIONAL_PATH```: if you want to transfer the videos to a specific path within the bucket, put the path in this variable **WITHOUT** the first and last ```/``` 
   - For example: if videos should be stored in ```/videos/project/january/```, the value in ```OPTIONAL_PATH``` must be ```videos/project/january```
 
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.
