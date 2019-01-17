## Notes taken at rstudio::conf 2019

> these are the tentative sessions I'll be attending. My main focus will be around R in Production, Reporting, and Databases.

### Day 1
---------
#### Welcome + RVision

- hitting 1700 attendees
- the way of RStudio
- R in Production
- Foocus on Reproducibility
- Repeatable/Insepectable/Reusable/Diffable Analysis
- Introducing "Launcher?" and Package Manager(Internal CRAN)... kubernetes environment
- Propose using rmarkdown in Connect for scheduled reporting
- Connection to spark/databases directly within IDE
- Cycle is to build high quality Open Source software by support of Enterprise/commerical clients who purchase commercial products

#### Keynote 1: Shiny in Production (Joe Cheng)

- Made it easy to run Shiny in Production in 2019 
- Challenges:
    - Cultural: don't realize; don't know best practice; don't anticipate/budget for the effort required; don't come from a culture that wrorries about runtime efficiency
    - Organizational: IT skeptical, conservatism; Skeptical of DS creating production artifacts; Skeptical of R as a technologies; Engeerining not on your side; 
    - Technical: Shiny addresses web app but effort wasn't made in SDE; R can be slow, multi-threaded
- shinytest (UI test)/shinyloadtest (Shiny test)/profvis (profiler)/Plot caching (speed up plots)/Async (Last resort to deal with slowiness)
- Workflow: shinyloadtest -> profvis -> work on code (refactor, dont loop... async) -> Repeat!
- Plot caching: reqs: slow plots; significant time spends; most users are likely to request the same few plots

#### API Development with R and TF at T-Mobile

- Business Story: "Unlock my phone", Recent Order = Yes -> Unlock Phone 80%
- Create an R File for the API endpoint -> Start Plumber Service -> Make HTTP request
- Use Dockerfile
- Plumber does not support HTTPS: Added an Apache 2 server to reroute
- Removed more file to decrease Docker size
- Lesson Learned: R&Plumber close to Python&Flask; Shiny demo sold the project! Flat and Agile structure: DS, Engineer, PM
- T-Mobile Blog: Enterprise Web Services with NN using R and TF
- nolisllc.com/rstudio19
- T-Mobile is hiring!

#### R in Production

- One weird trick to get R in Production, rinprod::run(...)
- Cultural barrier the most challenging like Joe's keynote

#### Databases using R


#### Working with categorical data in R

- use tidyverse::forcats

#### RStudio Job Launcher

- Not clear what this is...  Sounds like leveraging Docker to deploy projects with different resources/environments (kubernetes) easily. Need follow up.
- Available in RStudio Server Pro 1.2.0

#### Building an A/B Testing Analytics System

- Use `funneljoin` pacakge for A/B testing
- Takeaway: 
    1. Build tools to save yourself time
    2. Everything can go wrong, will go wrong
    3. Build tools that empower others
    4. Make it easy to do the right thing

#### Dashboards for Pioneering Genomic Medicines in R

- Google this: The 100,000 Genome Project
- dashboard needs to at least answer one question well
- When considering to scale up your shinyapp, use profvis, shinyloadtest for testing

#### Democratizing R with Plumber APIs

- Annotate with #*
- OpenAPI Specification
- Full specification can be manipulated at runtime
- Shiny is good but time to expose via API for broader audience (Software Engineer in other language) to consume

#### Tidy Time Series Analysis

#### 3D Mapping, Plotting with rayshader

#### Spatial Data Science in the Tidyverse

#### Getting it Right with Writing Reliable R Code



### Day 2
--------


