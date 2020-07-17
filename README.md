# Udacity Project on s3 and cloudFront

### Prerequisite

1. AWS Account

### Steps to practice this assignement

1. Create a bucket over s3

2. Copy `index.html`, `css/`, `img/`, `vendor/`

3. Under permission tab, select ***Block public access*** and  Turn off ***Block all public access***

4. Now go to Bucket Policy and the following policies. **Note:** Replace the Bucket-name against the *Resource* key

    ```json
    {
      "Version":"2012-10-17",
      "Statement":[
        {
          "Sid":"AddPerm",
          "Effect":"Allow",
          "Principal": "*",
          "Action":["s3:GetObject"],
          "Resource":["arn:aws:s3:::<bucket-name>/*"]
        }
      ]
    }
    ```

5. Under properties, Select Static website hosting. Check the option to use this bucket.

6. Put index.html as Index and Error document.

7. Now, Go to CloudFront and Create Distribution. 

8. Under Select delivery method, Click Get Started.

9. Under Origin setting, set the origin name as bucket-name and domain path as / and then create Distribution

10. Now wait for the status to become ***Deployed*** from ***InProgress*** 

11. Now hit the Domain name to access the [index.html](https://<domain-name>/index.html)


### Screenshots

All screenshots are under `screen-shots/` directory