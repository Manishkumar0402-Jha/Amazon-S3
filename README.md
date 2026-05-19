<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** manishkumar.jha0402@gmail.com  
**Email:** manishkumar.jha0402@gmail.com

---

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use Amazon S3 service to host static website. I'm doing this project to learn about AWS and cloud services and how they can be used to store objects in the cloud and even host websites (How does that work!?).

### Tools and concepts

Services I used were Amazon S3. Key concepts I learnt include bucket policies, uploading static website files, index.html, bucket endpoint URLs and ACLs and how they control access to our bucket's objects.

### Time, challenges, and wins

This project took me approximately 1.5 hours including demo time, quiz time and secret mission time. The most challenging part was resolving the 403 Forbidden error. It was most rewarding to see our webpage load live and be public to the world!

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will open S3 and then create a storage space inside to start storing website files.

### How long it took to create the bucket

Creating an S3 bucket took me less than 5 minutes. We needed to learn few new concepts like block public access and ACLs, but once that learning is done, we can create buckets even in shorter time in the furture.

### Region selection

The Region I have picked for my S3 bucket was Mumbai because it's the region that's closest to me. It's best practive to pick the region that's closest to you beacuse it lowers the time to retrieve your things (aka latency), and the cost.

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no two Amazon S3 buckets in the entire world can have the same name. They have to be completely unique regardless of the region or the account id.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will upload the website files into our S3 bucket. This is important because no files = no website! Our bucket is still empty, so lets get files inside so that we have a website to host!

### Files I uploaded

I uploaded two files to my S3 bucket - they were an index.html file ( this determines the structure i.e what goes inside your website) and folder of images and assets ( this will fill in the websites with the images and things we look at).

### How the files work together

Both files are necessary for this project as index.html determines the structure, but the structure alone does not illustrate the contents of the website. i.e if the index.html says " insert image here, it might not have the actual image to display - you need to supply that image separately. That's why we have multiple files uploaded - the index.html file to direct what is inside the website page, but also a bunch of assets (like images) that the website is tying to display.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will make our website available to the world! This is called static website hosting, and it's important because our website files will stay as 'just files' and not turn into a website if we don't do this step.

### Understanding website hosting

Website hosting means putting our website files on a web server, which is special computer designed to turn the files into a website page that people can visit.

### How I enabled website hosting

To enable website hosting with my S3 bucket, I went into the properties tab of our bucket, enabled static website and we also labeled "index.html" as our document, i.e this  is the document we're trying to host.

### Access Control Lists (ACLs)

An ACL (aka Access Cointrol List) is a way to configure permission settings inside a bucket. We enabled ACLs so that we can control access to our website files later. There was a pop-up metioning AWS recommends disabling ACLs , but I've keep it enabled to learn how ACLs work and compare it with bucket policies later.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is URL that takes you (and anyone on the internet) to the website that you're hosting!

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 forbidden error! The reason for this error was that the objects in a bucket are public by default - even though we've switched off "Block all Public Access" , the website files themselves are still completely private. We need to manage their access settings separately - they need to be public files too for the public to see the contents of our website.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will go to the files that we've uploaded into our bucket and make them public too because this will enable us to actually view the contents of our website! Once that's done, our website is officially live.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I have updated the access settings of the files inside our bucket too. Using ACLs, we made our bucket's files public! Once we checked our S3 bucket endpoint, we can see a webpage all loaded up.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

In this project extension I'm about to use bucket policies to control access to our bucket's files. I'm doing this so that we can stop people from deleting the objects inside the file!

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are rules that determine who is allowed (or NOT allowed) to do something. The benefit of using bucket policies is that you can have even greater control of the ACTIONS that people are/aren't allowed to do, while ACLs are useful for controlling public access to individual objects inside the bucket.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-host-a-website-on-s3_sm2sm2sm)

### What my bucket policy does

My bucket policy denies everyone from deleting our index.html file in the bucket. We tested this by trying to delete index.html and we saw a permission denied error! This means our bucket policy worked - it successfully stopped us from deleting the object we wanted to protect.

---

---
