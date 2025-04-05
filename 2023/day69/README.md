<<<<<<< HEAD
# #90DaysOfDevOps Challenge

## Learn, Upskill, Grow with the Community

Join our DevOps community challenge and embark on a 90-day journey to become a better DevOps practitioner. This repository serves as an open invitation to all DevOps enthusiasts who are looking to enhance their skills and knowledge. By participating in this challenge, you will have the opportunity to learn from others in the community, collaborate with like-minded individuals, and ultimately strengthen your DevOps abilities.

Let's come together to grow and achieve new heights in DevOps!

📖 **Discover More in Our Detailed Table of Contents!** Explore the richness of our content and find what you're looking for efficiently. Check out our [TOC here](./TOC.md).

## Steps:

- Fork[https://github.com/LondheShubham153/90DaysOfDevOps/fork] the Repo.
- Learn Everyday and add your learnings in the day wise folders.
- Check out what others are Learning and help/learn from them.
- Showcase your learnings on LinkedIn

## These are our community Links
  <a href="https://discord.com/channels/824622549182185493/824622550327623692">
    <img width="30px" src="https://www.vectorlogo.zone/logos/discordapp/discordapp-tile.svg" />
  </a>&ensp;
    <a href="https://t.me/trainwithshubham">
    <img width="30px" src="https://www.vectorlogo.zone/logos/telegram/telegram-icon.svg" />
  </a> 
  </a>&ensp;

  <a href="https://www.linkedin.com/in/shubhamlondhe1996/">
    <img width="30px" src="https://www.vectorlogo.zone/logos/linkedin/linkedin-icon.svg" />
  </a>&ensp;

 <a href="https://www.youtube.com/@TrainWithShubham">
  <img width="30px" src="https://i.pinimg.com/originals/46/02/cb/4602cbc18967da9c1eba7452905cd99b.png" />
  </a>&ensp;

  <a href="https://chat.whatsapp.com/FvRlAAZVxUhCUSZ0Y1s7KY">
  <img width="30px" src="https://www.vectorlogo.zone/logos/whatsapp/whatsapp-icon.svg" />
</a>&ensp;


<a href="https://www.trainwithshubham.com/">
  <img width="30px" src="https://media.licdn.com/dms/image/C4D0BAQGokBZsFEUWHw/company-logo_200_200/0/1677354328695?e=1700092800&v=beta&t=3bw7W2tQEpn023Slj_PacUZflE-OyYpBU-9juiJNJVY" />
</a>&ensp;

## Events

### YouTube Live Announcement:
<a href="https://youtu.be/rO5Rllir-LM">
  <img width="30px" src="https://i.pinimg.com/originals/46/02/cb/4602cbc18967da9c1eba7452905cd99b.png" />
  </a>&ensp;

### YouTube Playlist for DevOps:
<a href="https://youtube.com/playlist?list=PLlfy9GnSVerRqYJgVYO0UiExj5byjrW8u
">
  <img width="30px" src="https://i.pinimg.com/originals/46/02/cb/4602cbc18967da9c1eba7452905cd99b.png" />
  </a>&ensp;

### DevOps Course:
<a href="https://bit.ly/devops-batch-7">
  <img width="30px" src="https://media.licdn.com/dms/image/C4D0BAQGokBZsFEUWHw/company-logo_200_200/0/1677354328695?e=1700092800&v=beta&t=3bw7W2tQEpn023Slj_PacUZflE-OyYpBU-9juiJNJVY" />
</a>&ensp;

## Thanks to all contributors ❤

 <a href = "https://github.com/LondheShubham153/90DaysOfDevOps/graphs/contributors">
   <img src = "https://contrib.rocks/image?repo=LondheShubham153/90DaysOfDevOps"/>
 </a>
=======
# Day 69 - Meta-Arguments in Terraform

When you define a resource block in Terraform, by default, this specifies one resource that will be created. To manage several of the same resources, you can use either count or for_each, which removes the need to write a separate block of code for each one. Using these options reduces overhead and makes your code neater.

count is what is known as a ‘meta-argument’ defined by the Terraform language. Meta-arguments help achieve certain requirements within the resource block.

## Count

The count meta-argument accepts a whole number and creates the number of instances of the resource specified.

When each instance is created, it has its own distinct infrastructure object associated with it, so each can be managed separately. When the configuration is applied, each object can be created, destroyed, or updated as appropriate.

eg.

```

terraform {

required_providers {

aws = {

source = "hashicorp/aws"

version = "~> 4.16"

}

}

required_version = ">= 1.2.0"

}



provider "aws" {

region = "us-east-1"

}



resource "aws_instance" "server" {

count = 4



ami = "ami-08c40ec9ead489470"

instance_type = "t2.micro"



tags = {

Name = "Server ${count.index}"

}

}



```

## for_each

Like the count argument, the for_each meta-argument creates multiple instances of a module or resource block. However, instead of specifying the number of resources, the for_each meta-argument accepts a map or a set of strings. This is useful when multiple resources are required that have different values. Consider our Active directory groups example, with each group requiring a different owner.

```

terraform {

required_providers {

aws = {

source = "hashicorp/aws"

version = "~> 4.16"

}

}

required_version = ">= 1.2.0"

}



provider "aws" {

region = "us-east-1"

}



locals {

ami_ids = toset([

"ami-0b0dcb5067f052a63",

"ami-08c40ec9ead489470",

])

}



resource "aws_instance" "server" {

for_each = local.ami_ids



ami = each.key

instance_type = "t2.micro"

tags = {

Name = "Server ${each.key}"

}

}



Multiple key value iteration

locals {

ami_ids = {

"linux" :"ami-0b0dcb5067f052a63",

"ubuntu": "ami-08c40ec9ead489470",

}

}



resource "aws_instance" "server" {

for_each = local.ami_ids



ami = each.value

instance_type = "t2.micro"



tags = {

Name = "Server ${each.key}"

}

}

```

## Task-01

- Create the above Infrastructure as code and demonstrate the use of Count and for_each.
- Write about meta-arguments and its use in Terraform.

Happy learning :)

[← Previous Day](../day68/README.md) | [Next Day →](../day70/README.md)
>>>>>>> 9c88cfc (added)
