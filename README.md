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
- **shinytest (UI test)/shinyloadtest (Shiny test)/profvis (profiler)/Plot caching (speed up plots)/Async (Last resort to deal with slowiness)**
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
- **Shiny is good but time to expose via API for broader audience (Software Engineer in other language) to consume**

#### Tidy Time Series Analysis

#### 3D Mapping, Plotting with rayshader

#### Spatial Data Science in the Tidyverse

- How to tackle **Time-dependent** spatial data series? - spatiotemporal
- `stars` package

#### Getting it Right with Writing Reliable R Code

- How to determine code quality?
    - execution feedback
    - user feedback
    - best way, measure with tests: functional, integration, performance
- Unit test
- testthat, usethis::use_this/devtools/testit...
- helpful when developing packages
- for shiny test - shinytest
- some resources: Hadley's R Pacakge/Jenny Bryan's video on "Code smells and feels" from useR!2018

### Day 2
--------

#### R Markdown the Big Picture

- R Markdown - the definitive guide book
- 75% - 90% of preclinical results CANNOT be reproduced (estimate)...!!!
- 6 of 18 can be replicated in Economics, 13 of 21 in Nature & Science...!!!
- Cost of $28B in US alone
- Science vs. Math

#### Create Beautiful PDF with RMarkdown + CSS

- Believe in HTML and Web, because it's the most accessible. Easy to integrate images, table etc
- Package: `pagedown` (requires Pandoc 2.0)
- output types: pagedown::html_paged/pagedown::business_card/pagedown::html_resume/pagedown::poster_relaxed/pagedown::html_letter/pagedown::book_crc
- Don't waste time on trivial settings (typesetting in academia paper world). People spent too much effort on.

#### Introducing the gt package

- basic workflow: table data (tibble/data frame) -> gt object -> gt table
- Has table header, row labels, column labels, data formatting, footnotes
- **2 main function families: `tab_*`, `fmt_*`**
- many other great functions, check this out!
- Send email. `blastula`
- **Currently supports HTML/RTF/PDF, unable to export to Excel but in the pipeline**

#### The lazy and easily distracted report writer

- People easily get distracted from other people/meetings/jobs, so use rmarkdown report to track progress

#### Effective use of Shiny Modules in app development

- bit.ly/modules2019
- Facilitate Collaboration!
- Careful Design + Input & Return
- to () or not (), need practice
- Ames Housing App on Shiny gallery

#### Reactlog 2.0

- Built on cytoscape.js
- install_github("rstudio/reactlog") will be integrated in Shiny 1.3.0
- Cmd + F3 -> Awesome flow chart to show reactivity 

#### Integrating React.js and Shiny

- Idea came from MapboxGL
- bit.ly/reactR-tutorial
- github.com/react-R
- Why? You found a cool React-based lib and you want to use it from R. You want to build a cool React-based lib and use it from R
- React Component, 
    - very similar to HTML tags except: user-definable; 
    - Contain props and other Components
    - ...
- Make an HTMLWidget
    1. Scaffold R package with `usethis`
    2. Scaffold JS tool config with reactR
    3. Build JS with `yarn`/`webpack`
- Remaining work: inputs
    1. Shiny.onInputChange
    2. Goal: Send values without custom JS
    3. With Kent built 2 prototypes

#### Introducing ipc for Shiny


#### Keynote 3 - The Unreasonable Effectiveness of Public Work (David Robinson)

- Advocating public work - Tweet, Blog...
- Start a blog
    - Build a public portfolio
    - Practice writing and visualization
    - Teach/give advice in a way that _scales_
    - Use blogdown
    - Tweet @drob 
- Think about writing a book
    - Have a good amount to say
    - 

#### Panel Discussion

- When DS Failed?
    - DS should come out and say NO when there's need. Need to help PM to better navigate products. 
    - Build stuffs that have advantage over things that couldn've been done in Excel...
    - Avoid caring about models over actually business problems. Let go the ego.
    