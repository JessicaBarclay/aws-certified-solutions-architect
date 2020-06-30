
##### CloudFront

CDN(Content Delivery Network)
A system of distributed servers(network) that delivers webpages and other web content to a user based on the geographical locations of the user, the origin of the webpage and a content delivery server.

It can be used to deliver your entire website, including dynamic, static, streaming and interactive content using a global network on edge locations.
Requests are automatically routed to the nearest edge location, so content is delivered with the best performance possible
Edge locations ARE NOT read-only, you can write to them too(ie put an object on to them)
You can clear cached objects, but you will be charged - this is called invalidating the cache

Key terminology
Edge location
	This is a location where content will be cached. Seperate to a Region/AZ

Origin
	The origin of all the files that the CDN will distribute. This can be S3, an EC2 Instance, an ELB or R53.

Distribution
A collection of Edge Locations

Web Distribution
Typically used for Websites

RTMP
Used for media streaming(adobe flash)

How CloudFront works... 

A User in the USA makes a request to watch a video. The content is stored in S3 in EU-WEST-1(Ireland) this is called the ORIGIN
The request goes to the nearest edge location, aws then forwards the request on using the backbone network and gets the content from the Ireland hosted S3 bucket(the origin)
The content gets cached at the edge location the User made the request to, for however long the TTL is configured to(defined in seconds)
The User watches the video, if another user makes the same request to the same edge location before the TTL is up - that User will get the cached video.

CloudFront summary:

AWSs CDN offering

Terminology:
- Edge Location. The location where content will be cached
- Origin. Source of files that the CDN will distribute. Either S3 bucket, an EC2, ELB or Route53.
- Distribution. The name given to the CDN which consists of a collection of Edge Locations.
- Web Distribution. Typically used for Websites.
- RTMP. Used for Adobe media. Streaming
- Not readonly
- Transfer acceleration is a way of writing to CloudFront
- Objects cached for the life of the TTL(Time to Live) value is in seconds
- You can clear cached objects by invalidating them, but you will be charged.