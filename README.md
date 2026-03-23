# static-website-hosing-with-cdn
Static Website Hosting with CDN Host a fast, global static website on AWS S3 + CloudFront, with HTTPS, high performance, and step-by-step setup included.

**What is Static Website Hosting with CDN?**
Static website hosting means your website is made of fixed files like HTML, CSS, JS, images—nothing dynamic like PHP or databases.
You store these files somewhere online so people can access them.
CDN (Content Delivery Network) is a system of servers around the world that caches your files. When someone clicks your site, they get the files from the server closest to them, making it lightning-fast.

**What is S3?**
S3 (Simple Storage Service) is AWS’s cloud storage. Think of it as a giant, infinitely scalable hard drive in the cloud.
You can upload your HTML, CSS, JS, and images there.
S3 can serve these files as a website if you enable static website hosting.


**SETUP STEPS**
Step 1: Open VS Code and create a basic `index.html` file.
<img width="979" height="656" alt="image" src="https://github.com/user-attachments/assets/242b4319-5f35-4653-944d-5cbbccddb7e7" />

Step 2: In the AWS Console, search for **S3** and click on it.
<img width="979" height="470" alt="image" src="https://github.com/user-attachments/assets/ae7f3c46-efad-4737-9795-51103a7e3357" />

Step 3: After navigating to the Amazon S3 page, click on **“Create bucket.”**
<img width="979" height="473" alt="image" src="https://github.com/user-attachments/assets/55cec649-1dbc-4c2a-a5a3-0e25a40c7a8a" />

Step 4: Follow the steps as shown, change only the highlighted settings, and leave everything else as default.
<img width="979" height="450" alt="image" src="https://github.com/user-attachments/assets/d923af20-0799-4a95-9c61-9afa24ba4c95" />

Step 5: It’s important to uncheck the **“Block Public Access”** box and check the acknowledgment, since we want the website to be publicly accessible.
<img width="979" height="390" alt="image" src="https://github.com/user-attachments/assets/f4c06afd-615c-48dd-883a-25a6f5fc97e6" />

Step 6: After creating the bucket, click on the bucket you just created.
<img width="979" height="389" alt="image" src="https://github.com/user-attachments/assets/0fc68356-eca3-4df4-975b-d7a48385fd46" />

Step 7: Inside it, click on the **“Upload”** button.
<img width="979" height="363" alt="image" src="https://github.com/user-attachments/assets/37d481e7-218b-4109-91cb-579e763d0f69" />

Step 8: In the Upload section, click on **“Add files.”**
<img width="979" height="449" alt="image" src="https://github.com/user-attachments/assets/e3919392-5cb8-4363-823f-c14c93d8fb9f" />

Step 9: Upload the **“index.html”** file you created earlier.
<img width="979" height="252" alt="image" src="https://github.com/user-attachments/assets/74758b66-5876-4297-9759-1db267f7905e" />

Step 10: In your bucket, go to **Properties**, then under **Static website hosting**, click **“Edit.”**
<img width="979" height="412" alt="image" src="https://github.com/user-attachments/assets/239a7c1f-41a4-4212-9a59-de727dbae12a" />

Step 11: Inside that, click **“Enable”** and enter the document name (for now, just use your file name).
<img width="979" height="447" alt="image" src="https://github.com/user-attachments/assets/34480949-559c-4d48-8a61-71e748212b23" />

Step 12: Go to **“Bucket Policy,”** edit it, and add the required policy
(you can use the bucket policy file already uploaded in this repository).
<img width="979" height="447" alt="image" src="https://github.com/user-attachments/assets/67a0ade6-0138-488d-9ce7-66f806396f8a" />

Step 13: Now go to **Properties**, copy the **Object URL**, paste it into your browser, and check the result.
<img width="979" height="447" alt="image" src="https://github.com/user-attachments/assets/6ceda3ec-7927-4795-b83e-cb205cb16675" />

You will see an output similar to this.
<img width="979" height="461" alt="image" src="https://github.com/user-attachments/assets/9f99fa57-0997-436a-9a25-f1eb7b2f0415" />


~ ADDING CLOUDFRONT


**What is CloudFront?**
CloudFront is AWS’s Content Delivery Network (CDN).
Its job: take your website files (HTML, CSS, JS, images) from S3 and deliver them super fast to users worldwide.
It caches your files on servers all over the globe. So when someone in Europe visits your site hosted in an S3 bucket in the US, CloudFront serves the content from a nearby server—no waiting, instant load.

Step 1: In the Amazon Console, go to **“CloudFront.”**
<img width="979" height="470" alt="image" src="https://github.com/user-attachments/assets/765affa1-2c3c-4396-a7de-483d8913ecdd" />

Step 2: Inside it, click on **“Create Distribution.”**
<img width="979" height="464" alt="image" src="https://github.com/user-attachments/assets/ccc237f5-660d-4359-8c56-c50f705bf552" />

Step 3: Choose the **Free Tier** plan.
<img width="979" height="391" alt="image" src="https://github.com/user-attachments/assets/e90f7d74-686c-4487-a468-a1effd014589" />

Step 4: Give the distribution a name.
<img width="979" height="449" alt="image" src="https://github.com/user-attachments/assets/6d554af0-191a-4ccf-8d8f-b99d5fc21f3e" />

Step 5: Select **Amazon S3**, then in **Origin**, choose the bucket you created. You’ll see an option to enable the endpoint—please check it.
<img width="979" height="448" alt="image" src="https://github.com/user-attachments/assets/1a5bdb89-88d4-4aa5-97ab-fe42e29eccbc" />

Step 6: Your distribution should look like this.
<img width="979" height="445" alt="image" src="https://github.com/user-attachments/assets/abeaf17e-8485-451a-babd-f4e8a3f5a9d1" />

Step 7: Go to **Behaviors**, click on **“Default,”** and then click **“Edit.”**
<img width="979" height="469" alt="image" src="https://github.com/user-attachments/assets/f6206ed0-763d-4f90-bbe7-d3b419916944" />

Step 8: Under **Viewer Protocol Policy**, select **“Redirect HTTP to HTTPS.”** If that doesn’t work, choose **“HTTP and HTTPS.”**
<img width="979" height="499" alt="image" src="https://github.com/user-attachments/assets/1f8c1b0f-908f-4f31-8cb1-172789247657" />

Step 9: Inside the distribution, you’ll find your domain name—copy it and paste it into your browser.
<img width="979" height="417" alt="image" src="https://github.com/user-attachments/assets/655fae6f-f772-4ee6-bb7d-f6c653ebb290" />
<img width="979" height="415" alt="image" src="https://github.com/user-attachments/assets/6d572b54-755e-4863-b9e3-35723bd255f7" />

You can access this domain from other devices to verify that the website loads properly and works as expected.




