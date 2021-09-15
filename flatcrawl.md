---
layout: page
title: FlatCrawl
permalink: /projekte/flatcrawl/
category: Projekte
---

The purpose of the FlatCrawl project is to collect flats from different rental sites and expose them in a consistent shape. Eventually it lets users define custom searches and provides them with instant updates on new matching flats. **Clarification:** flats are not stored on the server. The purpose is not to create a competing portal, but to extend usability and help users find the right flat quickly by receiving updates from several sites without the hassle to setup and maintain different searches.

<div class="catalog">
<figure style="max-width:320px" markdown="1">
![alt text](/img/flatcrawl/start_search.gif)
<figcaption>Initiating a search and setting up basic filters.</figcaption>
</figure>

<figure style="max-width:320px" markdown="1">
![alt text](/img/flatcrawl/add_location.gif)
<figcaption>You can add your important places and you'll receive routing information for each found flat.</figcaption>
</figure>
</div>


## Architecture

<center>
<figure style="max-width:640px;" markdown="1">
![alt text](/docs/flatcrawl.svg)
<figcaption>Components involved in the flatcrawl service.</figcaption>
</figure>
</center>

Checkout the [main github project](https://github.com/floschnell/flatcrawl) to see how the infrastructure is setup and what the different components are in detail.

### Crawlers

The crawlers module is the part that is extracting (scraping) information from different rental portals. It will also enrich the flats with geo coordinations and eventually send the results to a RabbitMQ message broker. I used this project to experiment with the Rust programming language. It was a bit rough to get started, but now I am pretty fond of the language features and its speed. Last time I checked, it took around 1-2 seconds to crawl 18 pages and extract 260 pages on my 2016 Macbook Pro. [Checkout which crawlers are currently supported and get involved here](https://github.com/floschnell/flatcrawl-crawlers).

### RabbitMQ

Currently it only receives crawled flats from the *Crawlers* and forwards them to the *Processors*. In the future I would like to decouple the different enrichment steps and wire them together via the message broker. I could also imagine providing third parties access to consume messages from a certain topic on the broker.

### Processors

These consume crawled flats from the RabbitMQ, process/filter/enrich and eventually forward them to end-consumers. Find the [implementation of the processors here](https://github.com/floschnell/flatcrawl-processors).

### Webapp

A react frontend to edit searches quickly. You can [find the code on github](https://github.com/floschnell/flatcrawl-web).

<div markdown="1">
<figure style="max-width:400px" markdown="1">
![alt text](/img/flatcrawl/edit_search.gif)
<figcaption>Once the search is setup, you can edit it from a more convenient web interface.</figcaption>
</figure>
</div>