# Data Analytics

```bash

# https://medium.com/@avabhyankar22/using-colima-to-run-docker-and-kubernetes-locally-on-a-mac-5d8e0a13e1f
# https://github.com/abiosoft/colima
brew install colima
brew install qemu
colima start --profile amd --arch amd




# Stop any running instances
colima stop
colima delete
sudo rm -f /private/var/run/docker.sock # Remove the socket file if it exists
rm -rf ~/.lima/colima # Clean up Lima directory


limactl create --name=colima template://default # Creating an instance "colima" Proceed with the current configuration
colima start --network-address --arch aarch64 --memory 4 --disk 60 --vm-type=vz

colima start --arch aarch64 --memory 8 --disk 100 --vm-type=vz --network-address --mount-type=virtiofs

colima status
```

Step 2: Follow Localstack Getting Started Doc

https://app.localstack.cloud/getting-started


```bash
# Check if LocalStack is running properly:
docker ps | grep localstack

# Test LocalStack connectivity
aws --endpoint-url=http://localhost:4566 s3 ls

# AWS CLI Config for localstack
aws configure --profile localstack
AWS Access Key ID [None]: test
AWS Secret Access Key [None]: test
Default region name [None]: us-east-1
Default output format [None]: json
```


## Need awscli-local

```bash
brew install awscli-local
```


##  Create RedShift Instance 

https://docs.localstack.cloud/user-guide/aws/redshift/

```bash

# keep this in your bashrc file
REDSHIFT_CLUSTER_IDENTIFIER="redshiftcluster"
REDSHIFT_SCHEMA_NAME="public"
REDSHIFT_DATABASE_NAME="db1"
REDSHIFT_TABLE_NAME="sales"
REDSHIFT_USERNAME="crawlertestredshiftusername"
REDSHIFT_PASSWORD="crawlertestredshiftpassword"
GLUE_DATABASE_NAME="gluedb"
GLUE_CONNECTION_NAME="glueconnection"
GLUE_CRAWLER_NAME="gluecrawler"

source ~/.bashrc

awslocal redshift create-cluster \
      --cluster-identifier $REDSHIFT_CLUSTER_IDENTIFIER \
      --db-name $REDSHIFT_DATABASE_NAME \
      --master-username $REDSHIFT_USERNAME \
      --master-user-password $REDSHIFT_PASSWORD \
      --node-type n1
```