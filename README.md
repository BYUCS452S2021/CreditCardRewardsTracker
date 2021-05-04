# CreditCardRewardsTracker
_An application to suggest credit cards to use at specific merchants_

### Business

#### What do we do?

- Users log in
- Users manually enter what cards they have - Later, we might automate this
- We keep track of what rewards those cards offer, e.g., progress towards sign-up bonuses or rewards for spending in certain categories
- We keep track of what category merchants belong to, i.e., the way VISA/MC/AMEX/Discover code merchants
- We suggest cards to use at specific merchants - Later, we might automate this using location services

#### How will we monetize this?

- Ads
- A paid offering to remove ads
- Offers for coupons or rebates
- Refer users to new cards
- Refer users to merchants
- Aggregate data to be used in marketing

Long term, the plan is to expand or get acquired.

### Operations

We'd host this service in AWS using managed services that scale well. Ideally, we don't need to do much to _operate_ the service, beyond patching and enhancements.

Thus, most of the operations concerns are related to the business itself, not the service. As we expand, we'll hire people devoted to more specific tasks like sales or marketing.

### Legal

#### Business Structure

- Once we have a minimum viable product, the plan is to incorporate as an LLC in Delaware.
- At that point, we'll continue to build out our offering and we'll work on getting beta testers.
- Slightly longer term, the plan is to seek venture capital so that we can hire more developers and advertise more aggressively.

#### Potential Legal Concerns

- Once we start automating more things, like ingesting users credit cards or referring users to merchants, we'll need to worry about compliance with finance and security regulations.
- To keep our merchant codes up to date, we'll want to make data agreements with card processors. The VISA merchant codes, for example, are public. But keeping them up-to-date right now might require something like web-scraping on a regular interval. We'd rather something more efficient, like getting events via webhook whenever a merchant code is updated.

### Technical

The plan is to make a backend service using Node.js (JavaScript or TypeScript) that connects to a PostgreSQL database. At least for local development, we were going to stick both things in Docker containers, which should facilitate development and integration testing. Once we're ready, we'll host it on AWS in Fargate and RDS. Later, we'll probably use DynamoDB, which also conveniently can be containerized for local development.

We'll use all sorts of DevOps tools, like GitHub Actions for CI/CD and Terraform for deploying to AWS.

For the frontend, a mobile app would make the most sense, but I (Gary) have relatively little experience with that. So, depending on our available resources, we might end up with a web frontend instead.

### Social

We'll advertise this in personal-finance related forums.

### Help Needed

I'm looking for a few people to help split the workload, and especially to work on the frontend. Later on, we'll need more business folks.

If you're interested, please comment on [this issue](https://github.com/BYUCS452S2021/CreditCardRewardsTracker/issues/1).

### Disclaimers

This is a class project to explore database design and usage with relational and NoSQL databases.

We're being encouraged to create a minimum viable product and we're encouraged to keep it to 3-5 tables worth of data, which frankly, sounds pretty hard to do with this data set.

Realistically, this application would be hard to monetize. There are existing, well-established players in this space.
