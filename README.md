<h1>Automation of the creation of a bucket in Amazon S3 to host a static website using Cloudformation</h1>

<h2>Lab 1: Hosting a Static Website</h2>
Static websites or web-apps have fixed content. They can contain HTML pages, images, style sheets and javascript, and can interact with back-end services via REST API calls. Single Page Apps (SPAs) created by frameworks such as React or Angular can be served in this way.

You can easily host a static website or web-app on Amazon S3 by uploading the desired content and making it publicly accessible. No servers are required and you can use Amazon S3 to store and retrieve any amount of data at any time, from anywhere on the web.

<h3>Task 1: Create a bucket in Amazon S3</h3>
In this task, you will create an Amazon S3 bucket and configure it for static website hosting.

In the AWS Management Console on the Services menu, select S3, then click the Create Bucket button

For the bucket name use firstname-lastname-bucket (replace firstname and lastname with your first name and last name). Bucket names must be globally unique

Click the Next button, under Tags enter a tag with key set to Department and value set to Marketing, then click Next again

Public access for buckets is disabled by default, however for websites the files will need to be public. Deselect all of the options and then click Next and then click the Create bucket button

Click on the new bucket then click on the Properties tab, and click Static website hosting

Click on the Endpoint link, you should receive a 404 Not Found error because we haven't placed any files in the bucket yet. Leave the tab open in your web-browser as we will return to it later

Return to the tab that has the AWS Management Console, and click the Use this bucket to host a website radio button

For Index document enter index.html (you will need to enter this even though it is already displayed)

Click the Save button

<h3>Task 2: Upload Content to your Bucket</h3>
In this task, you will upload the static files to your bucket.

In the S3 Management console click the Overview tab

Click the Upload button and then the Add files button and select the 3 other files in this lab folder (index.html, script.js, style.css) and then click Upload

<h3>Task 3: Upload Content to your Bucket</h3>
Objects stored in Amazon S3 are private by default. This ensures that your organization's data remains secure. In this task, you will make the uploaded objects publicly accessible.

Return to the browser tab that was opened earlier with the 404 Not Found error and refresh the page. You should now see a 403 Forbidden error message. This is because the files in the bucket are still set to private access (the default).
There are several ways to make Amazon S3 objects public:

A Bucket Policy can be used to make a whole bucket public, or just a directory within a bucket.
An Access Control List (ACL) can be used to make individual objects public.
It is normally safer to make individual objects public, as this avoids other files in the bucket accidentally being made public, however if you know that all the files in the bucket should always be public then you can safely set the entire bucket public via a Bucket Policy

Return to the browser tab with the S3 Management console and select the checkbox next to all 3 files

Click the Actions menu and select Make public then click the Make public button

Return to the broswer tab that had the 403 Forbidden error and refresh the page. You should now see the website corresponding to the 3 files.

<h3>Task 4: Update the Website</h3>
You can make changes to the website by editing the HTML file and uploading it again to the Amazon S3 bucket.

On your computer, open the index.html file (in this lab folder) in a text or code editor. You could use Notepad (Windows) or TextEdit (Mac) or any other tool

Find the text Served from Amazon S3 and replace it with Created by firstname lastname (replace firstname and lastname with your own first name and last name)

Save the file and then return to the S3 Management console tab and upload the modified file to the bucket

Click the checkbox next to the index.html file and then the Actions menu and make the file public again

Return to the browser tab with the website and refresh the page and you should see it updated to show the modified text
