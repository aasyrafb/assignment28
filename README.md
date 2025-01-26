# assignment28

cd Asyraf Bahari\Documents\NTU-SCTP\2.8 Assignment

# Package the application
zip -r v0.0.2.zip .

# Upload the new version to Elastic Beanstalk
aws elasticbeanstalk create-application-version \
  --application-name "asyraf-python-app" \
  --version-label "0.0.2" \
  --source-bundle S3Bucket=my-bucket,S3Key=v0.0.2.zip

# Deploy the new version
aws elasticbeanstalk update-environment \
  --environment-name "asyraf-development" \
  --version-label "0.0.2"
