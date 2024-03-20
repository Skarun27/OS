
#### 1. Tell me about a time you failed:
* Ownership
* Learn and Be Curious
* Insist on the highest standards



#### 2. **Invent & Simplify**: Share examples of how you've created innovative solutions or streamlined processes?

##### Why Amazon?

I'm drawn to Amazon for its core commitment to customer obsession, a value that echoes my own ethos of prioritizing customer satisfaction, honed through years in on-call roles. My admiration extends to Amazon's innovation culture, from AWS to its ventures in generative AI, where solving complex problems at scale leads to groundbreaking solutions. The opportunity to contribute to products that could revolutionize the tech landscape, much like AWS, excites me. I look forward to applying my skills and embracing the challenges at Amazon, aiming to be part of a team that shapes the future of how we live and work.

### Customer Obsession

- Tell me about a time when you didn't meet customer expectations. What happened, and how did you deal with the situation / Tell me about a time you failed ?

**Situation**: 
While working at Zycus as part of an on-call team responsible for fixing client-reported issues within the Service Level Agreement (SLA), I encountered a situation where I was tasked with addressing a high-priority issue and simultaneously assigned to ship a Customer-Specific Change Request (CSCR) for a wrong order placed by a client. This order correction was critical for the client as they needed it to be part of their current sales quarter for audit purposes.

**Task**:
My task was to quickly generate and test a query to correct the order and ensure it met the client's urgent deadline, all while managing another high-priority issue.

**Action**: 
In my eagerness to address both tasks efficiently, I quickly created and locally tested the query for the CSCR without thoroughly verifying the order and product IDs. Believing it to be correct, I submitted the deliverables and closed the ticket. However, the ticket was reopened by the client due to verification failure; the query I provided contained incorrect IDs from the other issue I was working on, leading to an incorrect order correction and further complicating the situation. Realizing my mistake, I owned up to it and, along with my team, performed a rollback of the initial query and submitted a new, corrected query.

**Result**: 
This experience was a significant learning point early in my on-call role, ==highlighting the importance of meticulous attention to detail, especially when working under pressure. I learned the value of double-checking my work and the impact of my actions on client satisfaction and trust.== Following this incident, I adopted a more diligent approach to delivering work, consistently achieving a 95% success rate on our SLAs over two years. My commitment to high standards and continuous improvement was recognized during my tenure, and upon leaving the company after 3.5 years, I emphasized the importance of never taking shortcuts, especially in production environments, during my knowledge transfer sessions. This experience solidified my understanding of Ownership, Learning and Curiosity, and Insisting on the Highest Standards, principles that I've carried forward in my professional journey.



* How do you go about prioritizing customer needs when you are dealing with a large number of customers?

In dealing with a large number of customers, my first step is to understand and categorize their needs based on urgency and impact, using a severity matrix. This approach allows me to address critical issues that affect customer satisfaction and business operations first. I rely on customer data and feedback to inform these priorities, ensuring decisions are both data-driven and aligned with our strategic goals. Effective communication is key; I ensure customers are informed about the status of their requests, setting realistic expectations. For instance, at my previous job, I was once asked to join to the call where the stakeholders wanted me to deliver a task on priority, however, I had other tasks in my bucket that were of more priroity and severity and so I set a clear communication with my manager about the priority of the highlighted issue and eventually we reached on a consensus on the project delivery timeline. Continuous feedback loops with customers and internal teams help refine this process, ensuring we're always improving and meeting our customers' evolving needs.


### Ownership


*  Tell me about a time when you took on a task that was beyond your job responsibilities.

**Situation**: At Zycus, our product engineering teams were preparing for an upcoming quarterly release. Typically, senior members were assigned as points of contact due to the complexity of the process. However, during one critical cycle, all senior engineers were overwhelmed with work, leaving a gap in the assignment for the release coordinator.

**Task**: Despite being a junior engineer, I saw an opportunity to step up and volunteered to take on the role of coordinating the release. This involved demoing new features to stakeholders, preparing and tracking deliverables, and coordinating with sister teams and the release management team.

**Action**: I proactively immersed myself in all the necessary documentation and sought guidance from my manager whenever I encountered uncertainties. My commitment to understanding the process end-to-end enabled me to effectively communicate with all involved teams, ensuring that any dependencies or support needs were addressed promptly.

**Result**: Successfully shipping the release on time was a significant achievement, but the experience was invaluable for other reasons. It taught me the critical importance of timelines, commitments, and effective communication with internal teams. This role allowed me to contribute significantly to our team's success, reinforcing how collaboration and support across teams enhance organizational outcomes.



- Tell me about a time when you had to work on a task with unclear responsibilities.

**Situation**: At Zycus, our team embarked on integrating a new CI/CD pipeline utilizing Golang for scripting and Docker containers for execution environments. This initiative, primarily led by the DevOps team, aimed to streamline deployment processes across various products. However, the deployment of our specific product encountered persistent issues, entering a cycle of continuous problems that remained unresolved for days, affecting the development cycle and productivity.

**Task**: As the project encountered roadblocks, I was tasked with ensuring the successful deployment of our product using the new pipeline. The objective was to expedite our deployment times, thereby enhancing overall team productivity and introducing more efficient deployment practices.

**Action**:

- **Collaborative Diagnosis**: I initiated and led multiple meetings with the DevOps team to thoroughly understand the pipeline's foundation and identify the discrepancies causing deployment failures for our product.
- **Identifying the Root Cause**: Through detailed discussions and collaborative review, we pinpointed that the core issue lay in the generic deployment approach, which was incompatible with our product's unique architectural needs.
- **Solution Implementation**: Armed with this insight, the DevOps team tailored the pipeline to accommodate our product's specific requirements, effectively resolving the deployment challenges.

**Result**: This targeted intervention halved our deployment times from 40-50 minutes to 20 minutes, significantly boosting daily productivity and introducing zero downtime deployments—a first for the team. This breakthrough allowed for seamless patch deployments during weekdays without impacting production. Furthermore, resolving this issue, which had been a bottleneck for three months, markedly improved developer productivity. This experience underscored the value of diving deep to understand underlying issues and inventing simplified solutions tailored to specific challenges, principles that I carry forward in my professional endeavors.



* Tell me about a time when you showed an initiative to work on a challenging project.

Situation: In my previous role at zycus, I was working on an e-procurement product, which required to communicate and push notification to multiple other products, such as invoice on Buyer side and Order push to supplier side. Often we used to get issues where the notification of the order status change failed to reach to the other side. We weren' getting the transparency as to where the issue actually had occured. We have been just using the workaround of retriggering the notification, for such issues. 

Task: I wanted to solve this issue for once and for all. I convinced my manager to build an in-house messaging queue that would give us more control over the producer and consumer actions when a particular event was published and consumed. 

Action: I scheduled with multiple stakeholders to understand their issues so far with the MQ so that we don't miss out on any significant feature. I was assigned a senior engineer as my mentor for this work and I started gathering requirements, conducting brainstorming sessions, and eventually built the system that was durable and had an interface that would clearly show the events that weren't processed, or were processed but failed to process on the consumer end, or the issue started from the producer end itself. 

Result: We got a new centralized messaging system for our product that not only gave us transparency, but became a more durable, and reliable system. This reduced our incidents significantly, although I would say it was;t that perfect in the initial phase, and we were still improving it based on the feed back we received from our fellow developers. This experience taught me the value of taking the initiative and the impact of leveraging technology to solve practical business problems.


### Invent and Simplify

- Describe a time when you found a simple solution to a complex problem.

taking screenshots via screenshot library instead of watching the complete series of screenshots on browserstack

- Tell me about a time when you invented something.

Introduced Zyqualsquad that helped increased team bonding and spend some time aside from work  and learn something new from every member of the team

- Tell me about a time when you tried to simplify a process but failed. What would you have done differently?

While doing POC for Automation framework, suggested Katalon, which was simple to use but later realised will require too many customizations for a product with such complex features like us to operate on a record and run tool.



### Earn Trust

- Describe a time when you had to speak up in a difficult or uncomfortable environment.

I had to speak in the scrum meeting with the CEO in front of all the directors and 3 VPs from our engineering team in the absence of my manager / high priority client reported issue 



- What would you do to gain the trust of your team?


- Tell me about a time when you had to tell a harsh truth to someone.

Appraisal 0% to a resource, so conversation with her in the meeting



### Dive Deep

* Tell me about the most complicated problem you've had to deal with

Managing the project team for Foundation of Software Engineering, delivering in agile sprints and keeping up with the pace building team trust.

- Give me an example of when you utilized in-depth data to develop a solution

Research work - talk about thesis topic - decision to choose test smell based approach

- Tell me about something that you have learned in your role

philosophical and technical learnings both
philosophical - keep becoming better version of yourself, challenge yourself with new problem everytime, you will be amazed to see what you are capable of.
technical - My decision making became strong. It is easy to make decisions driven by data, you are confident on your decisions, and know that would work. No instinct based decisions. Thats what I love about Software Engineering.



### Have Backbone; Disagree and commit

- Describe a time when you disagreed with the approach of a team member. What did you do?

Bug re-open on float point number round up on price


- Give me an example of something you believe in that nobody else does.

- Tell me about an unpopular decision of yours.



### Deliver Results

- Describe the most challenging situation in your life and how you handled it.

Masters in the US and searching for job. 

- Give an example of a time when you had to handle a variety of assignments. What was the outcome?

On-call role, various responsibilities

- Tell me about a time when your team gave up on something, but you pushed them to deliver results.

Enabled team to fix issues faster to ship an epic and rather pushing it to next release (Blanket PO)



### Learn and Be Curious

- Tell me about an important lesson you learned over the past year
- Tell me about a situation or experience you went through that changed your way of thinking

On-call role learnings to work on priorities, and maintain clear communication

- Tell me about a time when you made a smarter decision with the help of your curiosity












