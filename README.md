# AWS-S3-Website_Hosting
Creating a html file of the website and adding that file to S3 bucket and running the website.

# Simple Storage Service (S3)

Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can use Amazon S3 to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics. Amazon S3 provides management features so that you can optimize, organize, and configure access to your data to meet your specific business, organizational, and compliance requirements.

# How Amazon S3 works:
Amazon S3 is an object storage service that stores data as objects within buckets. An object is a file and any metadata that describes the file. A bucket is a container for objects.
To store your data in Amazon S3, you first create a bucket and specify the bucket name and AWS Region. Then, you upload your data to that bucket as objects in Amazon S3. Each object has a key (or key name), which is the unique identifier for the object within the bucket.
S3 provides features that you can configure to support your specific use case. For example, you can use S3 Versioning to keep multiple versions of an object in the same bucket, which allows you to restore objects that are accidentally deleted or overwritten.
Buckets and the objects in them are private and can be accessed only if you explicitly grant access permissions. You can use bucket policies, AWS Identity and Access Management (IAM) policies, access control lists (ACLs), and S3 Access Points to manage access.
# S3 Key Details:
Objects (regular files or directories) are stored in S3 with a key, value, version ID, and metadata. They can also contain torrents and sub resources for access control lists which are basically permissions for the object itself.
The data consistency model for S3 ensures immediate read access for new objects after the initial PUT requests. These new objects are introduced into AWS for the first time and thus do not need to be updated anywhere so they are available immediately.
The data consistency model for S3 also ensures immediate read access for PUTS and DELETES of already existing objects, since Decembre 2020.
Amazon guarantees 99.999999999% (or 11 9s) durability for all S3 storage classes except its Reduced Redundancy Storage class.
## S3 comes with the following main features:
*	tiered storage and pricing variability
* lifecycle management to expire older content
*	versioning for version control
*	encryption for privacy
*	MFA deletes to prevent accidental or malicious removal of content.
*	Access control lists & bucket policies to secure the data.

## S3 charges by:
*	storage size
*	number of requests
*	storage management pricing (known as tiers)
*	data transfer pricing (objects leaving/entering AWS via the internet)
*	transfer acceleration (an optional speed increase for moving objects via Cloudfront)
*	cross region replication (more HA than offered by default)
Bucket policies secure data at the bucket level while access control lists secure data at the more granular object level. By default, all newly created buckets are private.
S3 can be configured to create access logs which can be shipped into another bucket in the current account or even a separate account all together. This makes it easy to monitor who accesses what inside S3.
There are 3 different ways to share S3 buckets across AWS accounts:
1.	For programmatic access only, use IAM & Bucket Policies to share entire buckets.
2.	For programmatic access only, use ACLs & Bucket Policies to share objects.
3.	For access via the console & the terminal, use cross-account IAM roles.
S3 is a great candidate for static website hosting. When you enable static website hosting for S3 you need both an index.html file and an error.html file. Static website hosting creates a website endpoint that can be accessed via the internet. When you upload new files and have versioning enabled, they will not inherit the properties of the previous version.
# Amazon S3 Storage Classes:
Amazon S3 offers a range of storage classes that you can choose from based on the performance, data access, resiliency, and cost requirements of your workloads. S3 storage classes are purpose-built to provide the lowest cost storage for different access patterns. S3 storage classes are ideal for virtually any use case, including those with demanding performance needs, data lakes, residency requirements, unknown or changing access patterns, or archival storage.
The S3 storage classes include. 
*	Amazon S3 Standard
*	Amazon S3 Intelligent-Tiering
*	Amazon S3 Standard-Infrequent Access
*	Amazon S3 One Zone-Infrequent Access
*	Amazon S3 Glacier Instant Retrieval
*	Amazon S3 Glacier Flexible Retrieval
*	Amazon S3 Glacier Deep Archive
Amazon S3 provides the most durable storage in the cloud. Based on its unique architecture, S3 is designed to exceed 99.999999999% (11 nines) data durability. Additionally, S3 stores data redundantly across a minimum of 3 Availability Zones by default, providing built-in resilience against widespread disaster. Customers can store data in a single AZ to minimize storage cost or latency, in multiple AZs for resilience against the permanent loss of an entire data center, or in multiple AWS Regions to meet geographic resilience requirements. If you have data residency requirements that can’t be met by an existing AWS Region, you can use the S3 Outposts storage class to store your S3 data on premises.
## 1.S3 Standard: The Go-to for Frequently Accessed Data

It is used for general purposes and offers high durability, availability, and performance object storage for frequently accessed data. S3 Standard is appropriate for a wide variety of use cases, including cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics.

Mainly it is used for general purposes to maintain durability, availability, and performance to a higher extent. Its applications are cloud applications, dynamic websites, content distribution, mobile & gaming apps as well as big data analysis or data mining.

Amazon S3 standard storage class is the versatile and widely used storage class in amazon S3. The following are some of the use cases of Amazon S3 standard class.

*	Hosting Static Websites.
*	Serving Content Distribution Networks (CDNs).
*	Storing Frequently Accessed Data.
*	Building Data Lakes and Data Warehouses.
*	Backing Up Data.
*	Serving Mobile and Gaming Applications.

Characteristics of  S3 Standard

*	Availability criteria are quite good, like 99.9%.
*	Improves the recovery of an object file.
*	It is against the events which are a little bit tough that can affect an entire Availability Zone.
*	 Durability of S3 standard is 99.999999999%.


## 2. S3 Intelligent-Tiering: Automated Cost Optimization for Data with Unknown Access Patterns

The first cloud storage automatically decreases the user’s storage cost. It provides very cost-effective access based on frequency, without affecting other performances. It also manages tough operations. Amazon S3 Intelligent – Tiering reduces the cost of granular objects automatically. No retrieval charges are there for Amazon S3 Intelligent – Tiering.

Characteristics of  S3 Intelligent-Tiering

*	Required less monitoring and automatically tier charge.
*	No minimum storage duration and no recovery charges are required to access the service.
*	Availability criteria are quite good, like 99.9%.
*	Durability of S3 Intelligent- Tiering is 99.999999999%.


## 3.S3 Standard-Infrequent Access: Cost-Effective Storage for Less Frequently Used Data

To access the less frequently used data, users use S3 Standard-IA. It requires rapid access when needed. We can achieve high strength, high output, and low bandwidth by using S3 Standard-IA. It is best in storing the backup, and recovery of data for a long time. It act as a data store for disaster recovery files.

To choose which type of data is suitable for the for S3 standard-infrequent access.

*	Access Frequency
*	Data Size
*	Access Latency Requirements
*	Data Durability Requirements
Characteristics of  S3 Standard-Infrequent Access

*	High performance and same action rate.
*	Very Durable in all AZs.
*	Availability is 99.9% in S3 Standard-IA.
*	Durability is 99.999999999%.


## 4. S3 Glacier Instant Retrieval: High-Performance Archiving with Rapid Retrieval

It is an archive storage class that delivers the lowest-cost storage for data archiving and is organized to provide you with the highest performance and with more flexibility. S3 Glacier Instant Retrieval delivers the fastest access to archive storage. Same as in S3 standard, Data retrieval in milliseconds.

Characteristics of S3 Glacier Instant Retrieval

*	It just takes milliseconds to recover the data.
*	The minimum object size should be 128KB.
*	Availability is 99.9% in S3 glacier Instant Retrieval.
*	Durability is 99.999999999%.


## 5. S3 One Zone-Infrequent Access: Cost-Optimized Storage for Single Availability Zone

Different from other S3 Storage Classes which store data in a minimum of three Availability Zones, S3 One Zone-IA stores data in a single Availability Zone and costs 20% less than S3 Standard-IA. It’s a very good choice for storing secondary backup copies of on-premises data or easily re-creatable data. S3 One Zone-IA provides you with the same high durability, high throughput, and low latency as in S3 Standard.

Characteristics of S3 One Zone-Infrequent Access
*	Supports SSL (Secure Sockets Layer) for data transferring and encryption of data.
*	Availability Zone destruction can damage the data.
*	Availability is 99.5% in S3 one Zone- Infrequent Access.
*	Durability is 99.999999999%.




## 6.S3 Glacier Flexible Retrieval: Balancing Cost and Retrieval Flexibility for Archiving

It provides low-cost storage compared to S3 Glacier Instant Retrieval. It is a suitable solution for backing up the data so that it can be recovered easily a few times in a year. It just takes minutes to access the data. 

Characteristics of S3 Glacier Flexible Retrieval

*	Free recoveries in high quantity.
*	AZs destruction can lead to difficulty in accessing data.
*	When you must retrieve large data sets, then S3 glacier flexible retrieval is best for backup and disaster recovery use cases.
*	Availability is 99.99% in S3 glacier flexible retrieval.
*	Durability is 99.999999999%.


## 7. Amazon S3 Glacier Deep Archive

The Glacier Deep Archive storage class is designed to provide long-lasting and secure long-term storage for large amounts of data at a price that is competitive with off-premises tape archival services that is very cheap. You no longer need to deal with expensive services. Accessibility is very much efficient, that it can restore data within 12 hours. This storage class is designed in such a way that users can easily get long-lasting and more secure storage for a huge amount of data at very less cost. Efficient accessibility and can restore data within very less time, therefore its time complexity is also efficient. S3 Glacier Deep Archive also has the feature of objects replication.

Characteristics of S3 Glacier Deep Archive

*	More secured storage.
*	Recovery time is less requiring less time.
*	Availability is 99.99% in S3 glacier deep archive.
*	Durability is 99.999999999%.
# S3 Encryption:
S3 data can be encrypted both in transit and at rest.
## Encryption In Transit:
When the traffic passing between one endpoint to another is indecipherable. Anyone eavesdropping between server A and server B won’t be able to make sense of the information passing by. Encryption in transit for S3 is always achieved by SSL/TLS.
## Encryption At Rest: 
When the immobile data sitting inside S3 is encrypted. If someone breaks into a server, they still won’t be able to access encrypted info within that server. Encryption at rest can be done either on the server-side or the client-side. The server-side is when S3 encrypts your data as it is being written to disk and decrypts it when you access it. The client-side is when you personally encrypt the object on your own and then upload it into S3 afterwards.
You can encrypt on the AWS supported server-side in the following ways:
*	S3 Managed Keys / SSE - S3 (server-side encryption S3) - when Amazon manages the encryption and decryption keys for you automatically. In this scenario, you concede a little control to Amazon in exchange for ease of use.
*	AWS Key Management Service / SSE - KMS - when Amazon and you both manage the encryption and decryption keys together.
*	Server-Side Encryption w/ customer provided keys / SSE - C - when I give Amazon my own keys that I manage. In this scenario, you concede ease of use in exchange for more control.
# S3 Versioning:
*	When versioning is enabled, S3 stores all versions of an object including all writes and even deletes.
*	It is a great feature for implicitly backing up content and for easy rollbacks in case of human error.
*	It can be thought of as analogous to Git.
*	Once versioning is enabled on a bucket, it cannot be disabled - only suspended.
*	Versioning integrates w/ lifecycle rules so you can set rules to expire or migrate data based on their version.
*	Versioning also has MFA delete capability to provide an additional layer of security.
# S3 Lifecycle Management:
*	Automates the movement of objects between the different storage tiers.
*	Can be used in conjunction with versioning.
*	Lifecycle rules can be applied to both current and previous versions of an object.
# S3 Cross Region Replication:
*	Cross region replication only works if versioning is enabled.
*	When cross region replication is enabled, no pre-existing data is transferred. Only new uploads into the original bucket are replicated. All subsequent updates are replicated.
*	When you replicate the contents of one bucket to another, you can change the ownership of the content if you want. You can also change the storage tier of the new bucket with the replicated content.
*	When files are deleted in the original bucket (via a delete marker as versioning prevents true deletions), those deletes are not replicated.
*	Cross Region Replication Overview
*	What is and isn’t replicated such as encrypted objects, deletes, items in glacier, etc.
# S3 Transfer Acceleration:
*	Transfer acceleration makes use of the CloudFront network by sending or receiving data at CDN points of presence (called edge locations) rather than slower uploads or downloads at the origin.
*	This is accomplished by uploading to a distinct URL for the edge location instead of the bucket itself. This is then transferred over the AWS network backbone at a much faster speed.
*	You can test transfer acceleration speed directly in comparison to regular uploads.
# S3 Event Notifications:
The Amazon S3 notification feature enables you to receive and send notifications when certain events happen in your bucket. To enable notifications, you must first configure the events you want Amazon S3 to publish (new object added, old object deleted, etc.) and the destinations where you want Amazon S3 to send the event notifications. Amazon S3 supports the following destinations where it can publish events:
*	Amazon Simple Notification Service (Amazon SNS) - A web service that coordinates and manages the delivery or sending of messages to be subscribing endpoints or clients.
*	Amazon Simple Queue Service (Amazon SQS) - SQS offers reliable and scalable hosted queues for storing messages as they travel between computers.
*	AWS Lambda - AWS Lambda is a compute service where you can upload your code and the service can run the code on your behalf using the AWS infrastructure. You package up and upload your custom code to AWS Lambda when you create a Lambda function. The S3 event triggering the Lambda function also can serve as the code's input.
# S3 and ElasticSearch:
*	If you are using S3 to store log files, ElasticSearch provides full search capabilities for logs and can be used to search through data stored in an S3 bucket.
*	You can integrate your ElasticSearch domain with S3 and Lambda. In this setup, any new logs received by S3 will trigger an event notification to Lambda, which in turn will then run your application code in the new log data. After your code finishes processing, the data will be streamed into your ElasticSearch domain and be available for observation.
Maximizing S3 Read/Write Performance:
*	If the request rate for reading and writing objects to S3 is extremely high, you can use sequential date-based naming for your prefixes to improve performance. Earlier versions of the AWS Docs also suggested using hash keys or random strings to prefix the object's name. In such cases, the partitions used to store the objects will be better distributed and therefore will allow better read/write performance on your objects.
*	If your S3 data is receiving a high number of GET requests from users, you should consider using Amazon CloudFront for performance optimization. By integrating CloudFront with S3, you can distribute content via CloudFront's cache to your users for lower latency and a higher data transfer rate. This also has the bonus of sending fewer direct requests to S3 which will reduce costs. For example, suppose that you have a few objects that are very popular. CloudFront fetches those objects from S3 and caches them. CloudFront can then serve future requests for the objects from its cache, reducing the total number of GET requests it sends to Amazon S3.
*	More information on how to ensure high performance in S3
# S3 Server Access Logging:
*	Server access logging provides detailed records for the requests that are made to a bucket. Server access logs are useful for many applications. For example, access log information can be useful in security and access audits. It can also help you learn about your customer base and better understand your Amazon S3 bill.
*	By default, logging is disabled. When logging is enabled, logs are saved to a bucket in the same AWS Region as the source bucket.
*	Each access log record provides details about a single access request, such as the requester, bucket name, request time, request action, response status, and an error code, if relevant.
*	It works in the following way:
*	S3 periodically collects access log records of the bucket you want to monitor.
*	S3 then consolidates those records into log files.
*	S3 finally uploads the log files to your secondary monitoring bucket as log objects.
# S3 Multipart Upload:
*	Multipart upload allows you to upload a single object as a set of parts. Each part is a contiguous portion of the object's data. You can upload these object parts independently and in any order.
*	Multipart uploads are recommended for files over 100 MB and is the only way to upload files over 5 GB. It achieves functionality by uploading your data in parallel to boost efficiency.
*	If transmission of any part fails, you can retransmit that part without affecting other parts. After all parts of your object are uploaded, Amazon S3 assembles these parts and creates the object.
*	Possible reasons for why you would want to use Multipart upload:
*	Multipart upload delivers the ability to begin an upload before you know the final object size.
*	Multipart upload delivers improved throughput.
*	Multipart upload delivers the ability to pause and resume object uploads.
*	Multipart upload delivers quick recovery from network issues.
*	You can use an AWS SDK to upload an object in parts. Alternatively, you can perform the same action via AWS CLI.
*	You can also parallelize downloads from S3 using byte-range fetches. If there's a failure during the download, the failure is localized just to the specific byte range and not the whole object.
# S3 pre-signed URLs:
*	All S3 objects are private by default, however the object owner of a private bucket with private objects can optionally share those objects without having to change the permissions of the bucket to be public.
*	This is done by creating a pre-signed URL. Using your own security credentials, you can grant time-limited permission to download or view your private S3 objects.
*	When you create a pre-signed URL for your S3 object, you must do the following:
*	Provide your security credentials.
*	Specify a bucket.
*	Specify an object key.
*	Specify the HTTP method (GET to download the object).
*	Specify the expiration date and time.
*	The pre-signed URLs are valid only for the specified duration and anyone who receives the pre-signed URL within that duration can then access the object.





# Hosting a static website on Amazon S3:
You can use Amazon S3 to host a static website. On a static website, individual webpages include static content. They might also contain client-side scripts. By contrast, a dynamic website relies on server-side processing, including server-side scripts, such as PHP, JSP, or ASP.NET. Amazon S3 does not support server-side scripting, but AWS has other resources for hosting dynamic websites. 
Firstly, we need to write the code for the webpages and check if the webpages are correctly displayed or working or not. After that, whatever the filename is we need to upload that file to the S3 bucket that we have created. And we need to upload the images or videos into the same S3 bucket which we are used in webpage content. Finally, we need to enable the website hosting option by clicking on the properties of the bucket. Now the website will be running on your S3 bucket. But you can only access that website from your amazon root account only. To allow access worldwide you need to make your bucket publicly accessible. Then only everyone throughout the world can access the website by using link that produced by the amazon S3. 
## Enabling website hosting:
When you configure a bucket as a static website, you must enable static website hosting, configure an index document, and set permissions.
To enable the static website, you need to follow some steps. They are:
1.	Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/.
2.	In the Buckets list, choose the name of the bucket that you want to enable static website hosting for.
3.	Choose Properties.
4.	Under Static website hosting, choose Edit.
5.	Choose Use this bucket to host a website.
6.	Under Static website hosting, choose Enable.
7.	In Index document, enter the file name of the index document, typically index.html (whatever your file name).
The index document name is case sensitive and must exactly match the file name of the HTML index document that you plan to upload to your S3 bucket. When you configure a bucket for website hosting, you must specify an index document. Amazon S3 returns this index document when requests are made to the root domain or any of the subfolders.
8.	(Optional) If you want to specify advanced redirection rules, in Redirection rules, enter JSON to describe the rules.
9.	Choose Save changes.
Amazon S3 enables static website hosting for your bucket. At the bottom of the page, under Static website hosting, you see the website endpoint for your bucket.
10.	Under Static website hosting, note the Endpoint.
The Endpoint is the Amazon S3 website endpoint for your bucket. After you finish configuring your bucket as a static website, you can use this endpoint to test your website.

As I mentioned above, our amazon S3 bucket must be publicly accessible to all. You can see in the below picture that my bucket is public.

![thopu](https://github.com/Agastya9799/AWS-S3-Website_Hosting/assets/157515904/eb65c205-8949-4f1e-ac8d-5d334397dd4d)
 

You can observe that all my files which I have uploaded are in the objects section. And if you need to add more files then by clicking on the upload option you can add more files.
	After enabling the static website hosting, you access your website. By copying the URL that has been on the html file. And open that URL in the new tab then you can see your website is running.
The below images are screenshots of the website that which I have running on the amazon S3.
 

 





 

 
