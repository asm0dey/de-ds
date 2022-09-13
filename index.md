---
marp: true
theme: gaia
size: 4K
class: default
paginate: true
footer: @asm0di0 &emsp13;&emsp13;@t_redactyl
backgroundImage: "linear-gradient(to bottom, #000 0%, #1a2028 50%, #293845 100%)"
color: white
title: Noname
---
<style>
footer {
    display: table
}
.hljs-variable { color: lightblue }
.hljs-string { color: lightgreen }
.hljs-params { color: lightpink }
</style>

<!--
_class: lead
_paginate: false
_footer: ""
-->

<!--
_class: lead
_paginate: false
_footer: ""
-->
# Avoid Hiring Data Ninja Rockstars
## How to build effective data teams

Dr. Jodie Burchell
Pasha Finkelshteyn

<!--
Hi everyone, I'm happy to be presenting today at Big Data London!

I'm Jodie Burchell, the data science developer advocate at JetBrains. I completed a PhD in psychology and a postdoc in biostatistics before moving into my current career in data science.

I prepared this talk with my colleague, Pasha Finkelshteyn, who is the Big Data developer advocate at JetBrains. Unfortunately he could not be here today, but this presentation is based on our collective decade plus of experience of working in data teams. I'd like to use this talk to clear up some misconceptions we've seen about what it takes to make a successful data team, including the different responsibilities and skills that need to be covered, and who is best able to check these off.
-->

---

## Who works with data?

<!--
To get started, I'd like you to think of the first role that pops into your mind when you think of who works with data.
-->

---

## Who works with data?

Of course, data scientists!

![bg right:40%](https://source.unsplash.com/BQGxNnyuFtU)

<!--
For many people, this would be a data scientist. In fact, the myth of what data scientists can do with data has only grown over the years I've been working in this role, with many companies imagining that if only they can hire one of these big brain PhDs they'll be making millions with AI products.
-->

---

## Who works with data?

Of course, data scientists! (not only)

![bg right:40%](https://source.unsplash.com/BQGxNnyuFtU)

<!--
Unfortuntately for these companies (and the ego of data scientists like myself), the picture is not that simple. Data scientists are not the only members of most data teams, and in many cases, may not be required, depending on what your company wants to do.
-->

---

# The reality is ...

Nobody should or even can do everything

Responsibilities should be distributed

<!--
In reality, unless you have a very small and early stage start up, no one person can or should do every task that falls under the data domain. 

I'm going to describe in this talk how these responsibilities would be typically distributed in a mature data team. 
-->

---

# Example project

Setup: Large fashion e-com _Trasos_

Task: recommender system

![bg right 70%](images/recommender_tweet.png)

<!--
To ground this talk a little, we're going to be using an example of a fairly typical problem that a data team might need to solve. Let's imagine that we work at a large fashion e-commerce called, I don't know, Trasos, and we'd like the data team to build a recommender system which suggests similar items to ones that they looked at or bought.
-->

---

# What the business says

- Increase retention
- Reduce cost of acquisition

<!--
The reason we want this recommender system is to retain customers that we already have, and also make it cheaper to get new customers ...
-->

---

<!-- _class: lead -->

# What does the business mean?

Clients be like

![](https://i.giphy.com/media/Qv5TjYPMeesh3ALM4N/giphy.webp)

<!--
... which we're hoping, of course, leads to more sales and more revenue. So I hope you can see we're not dealing with some abstract data problem here, but something that will directly improve the bottom line of the business.
-->

---

# Business outcomes

- It should be easier to convert non-customers to customers
- Customers should return sooner

<!--
Concretely, what we want this recommender system to do is increase the rate of converting non-customers, making this a cheaper way of acquiring new customers. In addition, we want to increase engagement and sales among existing customers.
-->

---

# Technical constraints

![bg right:30%](https://i.giphy.com/media/3o7TKMlDDXVFNqC5EI/giphy.webp)

- Lots of simple events (clicks, scrolls, interactions)
- Backend is in Scala, but Data Science team works with Python

<!--
We also have a number of technical constraints which will affect our recommender project. Our data is massive and made up of a bunch of simple events, which will need to be processed and converted into things we can actually use to train and measure our model. In addition, our backend is written in Scala but our data science team works in Python, so any model the data science team comes up with will need to coexist with a Scala code base.
-->

---

# Approach

1. Define business questions 
1. Define required data
1. Prepare data
1. Research models
1. Productionise model
1. Monitor

<!--
So, now that we understand what the business needs and what our technical limitations are, let's get to spelling out exactly what needs to be done to implement this project. 

The first thing we need to do is concretely define the business question. How much do we need to improve acquisition and retention for this project to be a success? How are we going to measure it, and will we compare this with a baseline, such as manually doing advertising?

Once we've worked this out, we need to define what the required data is for building the models and measuring this impact.

Following that, we need to prepare this data, firstly creating samples for building the model, and then designing the pipelines that will be used when the recommender is productionised.

Next, we get to (for me) the fun part, which is researching models. I think a lot of people think of this as the biggest and most important part of the project, but in fact as we'll see, it's a relatively small part compared to some others. The models that will be suitable depends on the data we have, how much time we have to experiment, how much uplift in retention and acquisition the business is expecting, and our technical constraints.

Once we've decided on a model that meets our criteria, we can productionise it, which includes plumbing up the data pipelines, serving the model, and making sure the results are implemented on the front end.

Finally, we need to build monitoring, which includes technical monitoring about how the data and the model is working, but also business reporting on how well the model is satisfying the business criteria, the whole reason we started this project in the first place!
-->

---

# Data skills

![bg](images/domain.jpg)

<!--
Now this is a big list of work, and I think you can see it requires many different skills. We can broadly divide these skills up into three areas. The first of these is domain knowledge, which is having a deep understanding of what the business does, and what kind of things would help the business improve or succeed. Analysts are deep domain specialists.
-->

---

# Data skills

![bg](images/domain-science.jpg)

<!--
The second area is science. This is using research skills in conjunction with data to answer open ended business questions or create useful data products. While data scientists tend spend most of their time in this domain, data analysts also need to do some research as part of their role. A common data analyst title in companies is a business intelligence analyst.
-->

---

# Data skills

![bg](images/domain-science-engineering.jpg)

<!--
The final area is engineering. Data engineering, the specific branch we'll be talking about in this talk, is organising, processing and storing data, which gets more and more complicated the bigger the data is. They may also be responsible for productionising machine learning models.

Data engineers with a deep domain knowledge are analytics engineers, who translate business needs into data models. People who have a command of data science and data engineering work are ML engineers, who are usually able to work on data science models and also understand how to get them into production.

Finally, at the intersection of all of these, we have our Data Ninja Rockstar, a person who we're asking to have a deep understanding of all of the business needs and current operations, excellent research skills and be a proficient engineer. Having spelled out all of the skills and responsibilities we might expect our Ninja Rockstar to have, you can see why they are true unicorns when it comes to hiring, especially for larger companies with more complex needs. In fact, in my last job we tried to hire a just a machine learning engineer and it took over a year to do so.

As you can probably guess from the title of the talk, I'm going to caution against trying to hire this all-in-one person to do everything on your data team and instead describe the three roles that typically divide up this work.
-->

---

<!-- _class: lead -->
# <!-- fit --> The three roles

---

<!-- _class: lead -->

# <!-- fit --> Data Scientists

The research folk

<!--
The first role in the data team we're going to talk about are the data scientists, or the research folk.
-->

---

# Data scientist skills

* Data + science!
* Automate manual processes
* Build data products
* Statistics
* Machine/deep learning
* Programming + data wrangling
* Data visualisation

<!--
What do data scientists do? Well, it's in the name - data and science, so their skillset is concerned with doing research with your company's data. What does this mean? Why would you hire a data scientist?

You might hire a data scientist to automate processes within your company that are being done manually. This might be rating the quality of leads for a call centre, or finding terms that will improve a search engine, or in this case, replacing manual acquisition efforts with a recommender. You might also use your data scientists to create data products, which either increase the value of your existing product or give you something you can sell externally. So, for example, in my last role I was in charge of creating audiences from people's mobile data, which allowed advertisers to buy ads targeting their group of choice.

Some of the core skills that data scientists use to do their work include statistics, to get certainty about their answers, and know machine and deep learning techniques to build predictive models. They also do some programming, but their programming skills are not the same as hardcore engineers. They tend only build proofs of concept, and as such they mainly use use R, which is a statistical programming language, or scientific packages within Python. A very small group are still using Julia - maybe their time will come someday. So you don't need to hire data scientists who can work in your backend systems, and who know languages like C or Rust or JVM languages, it's simply not required for their role.

Data scientists also do visualisation, in the context of presenting or understanding their research work. 
-->

---

# Data scientist responsibilities

* Translate business question
* Research available data and make shortlist
* Request sample from data engineering

<!--
What responsibilities would our data scientists have on our recommender project? Well, at the beginning, they would be responsible for working with the business stakeholders to understand if their request makes sense - is a recommender the best solution for this problem? They also need to estimate and communicate the complexity of building the model, to help work out whether the effort is going worth it, compared to the current process for getting and retaining customers. Machine learning solutions have a cost in terms of development and maintenance, and they are not necessarily better than manual processes.

They would then start by digging through all available data and putting together a shortlist of what looks like it could be useful for the model. After that, depending on how hard the data is to access, the data scientist will either pull a sample of this data themselves or ask data engineering to do so.
-->

---

# Data scientist responsibilities


* Feature engineering
* Iteratively find suitable model MVP
* Handover of model for productionisation
* Define model metrics, request monitoring

<!--
Now, to the fun part - the model creation. The data scientist will first start preparing the data for modelling, a process known as feature engineering. They will then iterate through different models and check their performance, keeping in mind both the business goals and the technical constraints. For example, it might be possible to meet the business goals with a relatively simple model that can be implemented in pure Scala, or we might need a more complex model that needs to be served with a platform such as MLflow. This is a collaborative process, as the data scientist needs to make sure that the minimum viable model is acceptable to both the business and engineering sides.

Once everyone agrees what an acceptable model looks like, it's time to productionise. Where the roles of data science end and engineering begin is highly team dependent, and I'll discuss this more at the end of the talk.

Finally, the data scientist will create monitoring to check how well their model is going in production.
-->

---

<!-- _class: lead -->

# <!-- fit --> BI Analysts

The data communication folk

<!--
The next role in the data team we're going to discuss is the business intelligence analysts, the data communication folk.
-->

---

# BI analyst skills

* Deep understanding of business
* Knowledge of what data answers business questions
* Data communication and visualisation
* Data wrangling
* Data exploration and analysis

<!--
In contrast to the data science team, BI analysts are responsible for understanding the business-as-usual. They need to know what information business people need to know about how the company is functioning and how to extract this from the data. 

Much of their work concerns communicating these findings to business people, either through creating dashboards to monitor core business metrics, or adhoc reports to answer business questions, which requires very high level data visualisation and story telling skills. They are typically good at data cleaning, usually through tools like Excel or SQL, and are skilled at exploring and analysing data.
-->

---

# BI analyst responsibilities

* Understand feasibility of project
* Define metrics for measuring business success
* Request sample from data engineering

<!--
What responsibilities will our BI analyst have on our recommender project? Well, they will work with business and data science to help understand if the retention and acquisition goals that we have are even feasible, based on past measures to improve these metrics. They'll also be able to find out the monetary impact of these improvements - again, the thing that actually matters here!

The BI analyst will then need to define the metrics to measure business success, and how to derive these from the raw data. Again, depending on how hard it is to access the data, they may pull a sample themselves or request one from the data engineering team.
-->

---

# BI analyst responsibilities

* Request final pipelines from DE for reporting
* Creating dashboards for business metrics
* Adhoc reporting

<!--
Once the recommender MVP is ready for production, the BI analyst will work with data engineering to create pipelines for the data they need to monitor those business metrics. In addition, they may define experiments in order to draw their conclusions about model, such as only applying the recommender to part of the customer base in order to have a baseline to compare to. 

Following this, they will build their monitoring, which is typically dashboards using tools such as PowerBI or Tableau. The analyst will be primarily responsible for monitoring how well the model is improving acquisition, retention and revenue, and communicating with both business and data science if the model doesn't seem to be performing as expected. In addition, they may need to create adhoc analyses about the performance of the recommender, such as pulling the numbers for piece for marketing to show off the cool technology that Trasos is using.
-->

---

<!-- _class: lead -->

# <!-- fit --> Data Engineers

The big data folk

<!--
Finally, we have our third role on the data team, the data engineers, or the big data folk.

-->

---

# Data engineer skills

* Data lifecycle
* Strong engineering skills
* Monitoring data pipelines
* Manage data needs for multiple teams
* (Sometimes) responsible for ML models in production

<!--
The main job of the data engineer is to deal with the data lifecycle. In contrast to data scientists, who usually deal with static samples of data, data engineers work with living data which enters the business in a constant stream. The four components of the data lifecycle are the consumption, processing and storage of this data, and then making this data available to others. Most data is stored and accessed through cloud services, for example, AWS S3 buckets or database servers such as Google's BigQuery. Key things that data engineers have to worry about is the cost of storaging and accessing data and the latency of processing it, and all of this is heavily dependent on the size and usage of the data.

In order to do all of this work, the data engineer needs strong engineering skills - no big surprise. The languages they are proficient in depends heavily on the team, but in our case, the data engineers are mainly working in Scala but can also write some Python to help out the data science team. The data engineer will need to create stable, well-tested and maintainable code which produces deterministic results, in order to make sure the incoming data is processed smoothly with predictable outputs. You can see that the goal and scope of their code is quite different from what the data scientist is doing.

Now, of course to make sure that everything is working properly, the data engineer also needs to set up monitoring of their data pipelines. They might set up alerts to check that the data are behaving as expected, and depending on how mission critical the data are, might be on pager duty to fix any expected problems.

As data tends to be one of the core parts of any business, the data engineer will also work with other teams. For example, business intelligence analysts might need the data engineer to create tables for them to build monthly reports from, rather than them needing to pull the raw data every time they need to update their dashboards.

Finally, the data engineering team will sometimes be responsible for ML models in production. We'll talk more about this in the rest of the talk.
-->

---

# Data engineer responsibilities

* Understand whether the data will support the project
* Tracking down data
* Extracting samples

<!--
So, let's look at the role our data engineering team will play on the recommender project. The data engineering team can help us understand from the outset whether there are likely to be any issues with the data that will make the project unfeasible, such as missing events or low coverage. 

They can then point the data science team in the right direction to start tracking down their data shortlist, and then once that shortlist has been put together, potentially help them with extracting their samples. As I've already said, they will also help the BI analysts get a sample of data for testing model metrics. As our data are huge and they're made up of lots of individual events, it may not be feasible for the data science or BI teams to pull this data themselves.
-->

---

# Data engineer responsibilities

* Build data pipelines for project
* (Potentially) implement model
* Monitor data

<!--
As we've already discussed, the data engineer will help the data scientist decide on an appropriate model from an implementation perspective. Once the model is completed, the data engineer has to do a lot of heavy lifting. They will be responsible for building the data pipelines to preprocess and feed data into the models, as well as capture the outputs. They'll also need to potentially build new pipelines to provide data for the BI analysts to do their reporting. They may also be responsible for implementing the model, which we'll talk about more in the next section. Finally, they need to add monitoring for the new data pipelines, and they may need to help the data scientists set up their monitoring.
-->

---

# Overlaps: Productionisation

* What is the definition of done for the finished model?
* Who is responsible when things go wrong?

<!--
I've made this distinction between roles sound quite neat, but there are quite a few areas where the division between roles is not so clear cut. We already mentioned one earlier, which is where that hand off point is between the data scientist finishing their model and the data engineering team implementing it.

In my experience, the approach can range from throw a Jupyter notebook over the fence and let engineering deal with it, to data science is on pager duty because they deployed the model, and I can tell you that neither extreme works that well. Instead, there is a large grey area and where that hand off point is going to be dependent on the skills and interests of both your data scientists and your data engineers.

When the model is being developed, there should be a prearranged definition of done, and an understanding of what the data engineering team will be responsible for. My general feeling is that whoever needs to be responsible for debugging this model in production should be the one who writes the code for it. So if your model is going to be served from MLflow, for instance, it might be better if your data scientists wrote the code for the model, but if the code is able to be written in Scala, then obviously your data engineering team needs to be responsible for that.

Another area where there will be overlap is when things go wrong. One of the reasons we've emphasised having a division of monitoring is so that the right team with the right expertise can spot problems in a timely manner. For example, the data science monitoring might show a massive drop in model performance, or the data engineering monitoring might show a huge drop off in events used for the model. Once the problem is found, it's likely going to be an exploratory process to diagnose it, which will involve multiple people from multiple teams, including people outside of data such as the ops team.
-->

---

# Summary

1. There are lots of responsibilities around data
2. These responsibilities are broad
4. You need to split your work between 3 dimensions
5. Hire team accordingly

![bg right](https://shirtoid.com/wp-content/uploads/2010/01/platypus.jpg)

---

<!-- _class: lead -->

# <!-- fit --> Thank you!

Twitter: @asm0di0


Blog: t-redactyl.io 
Twitter: @t-redactyl