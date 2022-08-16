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
# Data Ninja Rockstar 
# Is Not Enough

Jodie Burchell
Pasha Finkelshteyn

---

## Who works with data?

![bg right:40%](https://source.unsplash.com/BQGxNnyuFtU)

---

## Who works with data?

Of course, data scientists!

![bg right:40%](https://source.unsplash.com/BQGxNnyuFtU)

---

## Who works with data?

Of course, data scientists! (not only)

![bg right:40%](https://source.unsplash.com/BQGxNnyuFtU)

---

# Reality is

Nobody should or even can do everything

Responsibilities should be distributed

Some responsibilities can be "outsourced" to SaaS's

---

# Example?

Setup: Large fashion e-com (_Sapando?_)

Task: recommender system

---

# What business says:

- Increase retention
- Reduce cost of acquisition

---

<!-- _class: lead -->

# What business means?

Clients be like

![](https://i.giphy.com/media/Qv5TjYPMeesh3ALM4N/giphy.webp)

---

# What business means?

- Customers and even potential customers should return sooner
- It should be easier to convert non-customers to customers

---

# Technical constraints

![bg right:30%](https://i.giphy.com/media/3o7TKMlDDXVFNqC5EI/giphy.webp)

- Lots of simple events (clicks, scrolls, interactions)
- Backend is in Scala, but Data Science team works with Python

---

# Approach

1. Define business questions 
1. Define required data
1. Prepare data
1. Research models
1. Productionise model
1. Monitor


---

# Data components

![bg](images/domain.jpg)

---

# Data components

![bg](images/domain-science.jpg)


---

# Data components

![bg](images/domain-science-engineering.jpg)

---

<!-- _class: lead -->
# The three specializations
---

<!-- _class: lead -->

# <!-- fit --> Data Engineers

The big data folk

---

# Big data?

* Data that won't fit a single node
* Data that scales on 3V
    * Velocity
    * Variety
    * Volume
* Data on which we can make reliable business decisions


---

# Data engineer responsibilities

Data:

* Events

---

# Data engineer responsibilities

Data preparation:

* Collection and storage (managing costs)
* Verification (data engineering, upstream customers)

---

# Data engineer responsibilities

Technical solution:

* Configuration
* Technical solution and choice

---

# Data engineer responsibilities

In production:

* Monitoring (ops)
* Provide access to suitable data to BI and DS

---

# Data scientist responsibilities

<!-- Jodie, please split! -->

* Find a suitable technical solution
* Discuss constraints with business and engineering
* Request suitable data from DE
* Build MVP, assess success, test
* Define DoD for “production ready” in collaboration with DE team
* Extracting features from images and item metadata
* Data science metrics monitoring

---

# Data analyst responsibilities

Collaborate with data scientists to understand what business outcomes should be for the product
Downstream customer of data engineers, request required data for reporting (might involve asking DE to make dedicated ETLs because data will be required for long term reporting)
Create business metrics from raw clicks and scrolls - retention, acquisition and conversion behaviours
Build dashboards for reporting impact of business metrics on 
Connect business metrics with financial impact of project - relationship between retention, acquisition and conversion and financial performance
Create adhoc requests about the project for e.g., marketing team

---

# Data analyst responsibilities

![bg fit 80%](https://cdnl.tblsft.com/sites/default/files/blog/2_45.png)

---

# Overlaps: Productionisation

* What is the definition of done for the finished model?
* Who is responsible for each bit?
    * Responsible for algorithm: DS
    * Responsible for upstream data: DE
    * Responsible resourcing: ops
* What “production ready” code means

---

# Overlaps: Diagnose/fix

* Monitoring (from ops and DE) should pick up issue
* It’s a team effort (DE and DS) to diagnose
* Major changes should be an agreement between DE and DS

---

# Other roles

---

# Summary

1. There are lots of responsibilities around data
2. These responsibilities are broad
4. You need to split your work between 3 dimensions
5. Hire team accordingly

![bg right](https://shirtoid.com/wp-content/uploads/2010/01/platypus.jpg)

---

# TY!
