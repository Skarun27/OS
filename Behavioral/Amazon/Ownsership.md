*  Tell me about a time when you took on a task that was beyond your job responsibilities.

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