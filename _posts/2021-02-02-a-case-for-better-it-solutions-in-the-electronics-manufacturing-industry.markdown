---
layout: post
title:  "A case for better IT solutions in the Electronics Manufacturing Industry"
date:   2021-02-02 14:28:52 -0300
tag: electronics manufacturing
tag: enterprise software
tag: mrp
---
# Introduction

Electronic manufacturing is a complex operation to manage. In this first article I will describe one of the ways in which this complexity is expressed and the role of computer systems in its administration. Finally I will discuss how recent advances in Information Technology have revolutionized the way of developing software, opening the way to new and better tools.

# Discrete manufacturing - product complexity
The manufacture of electronic products is of discrete type, characterized by the production of perfectly distinguishable units.

These units are made up of multiple parts that are combined into a finished product (typically through several stages) during the manufacturing process. The structure of the product, expressed by a Bill Of Materials (BOM), shows the totality of the component parts and their groupings (subassemblies) within the product. In this way, we can think that there are then 2 "dimensions" in the complexity of the structure: the total number of parts and the total number of subassemblies. In general, the greater the number of any of these dimensions, the greater the difficulty in exerting precise control over the manufacturing operation and its costs.

In the particular case of the manufacture of electronic products, it is common for a factory to have an active catalog with dozens of different products, each of which having:
Number of unique components: tens to a few hundred, total components: hundreds to a few thousands.
Number of subassemblies: units up to a few tens.

These two “dimensions” of complexity impact on different, but interrelated issues:
Difficult inventory control, both for parts and subassemblies (WIP inventory)
Difficult production planning and control.

How does this impact companies? By increasing the inefficiency in the use of the two most important resources, which represent most of the variable cost of the operation: raw material and direct labor.

# The numbers (in Tierra del Fuego, Argentina)

The data used in this section comes from [official sources](https://ipiec.tierradelfuego.gob.ar/wp-content/uploads/2015/12/Anuario_2014.pdf){:target="_blank"}, except where otherwise noted.

The two most important variable costs in electronics manufacturing are raw materials and direct labor. The following table shows the annual production volume averages (period 2010-2014) across the top 3 categories of products, the average cost of the kits and the annual losses due to obsolescence (the asterisked fields are estimates, or calculations based on estimates ):

|                  | Units | Average cost * | Total cost *     | Obsolescence * | Total loss * |
| ------------------ | ------------ | ----------------- - | ------------------- | ----------------- | ---------- ------- |
| TVs      | 2,000,000 | USD 250          | USD 500,000,000 | 0.80%           | USD 4,000,000 |
| Cell phones        | 10,000,000 | USD 200          | USD 2,000,000,000 | 0.15%           | USD 3,000,000 |
| Conditioners | 1,000,000 | USD 350          | USD 350,000,000 | 0.80%           | USD 2,800,000 |
|                  |            |                  |                   |                 | USD 9,800,000 |

What is obsolescence? There is an excellent [article on Wikipedia](https://en.m.wikipedia.org/wiki/Obsolescence){:target="_blank"} that explains the phenomenon in more detail. According to this article, obsolescence is "the transition from availability to unavailability of a product by its original manufacturer or supplier", and occurs in the electronics industry when new models replace previous models, generally due to the introduction of technological improvements (specially in rapid evolution products such as phones and TVs).

This simply means that as a model approaches the end of its life cycle, it becomes impossible to replace parts that are routinely lost during manufacturing. And the greater the complexity of the products, the greater the probability of loss of individual parts.

Regarding labor, the following table describes the situation for the same period (2010-2014):

| Direct employment | Annual cost * | Total cost *     | Labor utilization* | Total loss * |
| ------------------ | --------------- | -------------- ----- | ----------------------- | ------------------ |
| 10,000           | USD 15,000 | USD 150,000,000 | 85%                   | USD 22,500,000 |

Labor utilization is the ratio between the hours effectively applied to the operation (paid to workers by the company) and the hours obtained as work content of the manufactured products (standard time multiplied by quantity produced).

Currently the production levels are close to half of the values ​​recorded in the previous tables. If we consider that the period 2010-2014 was a peak, and that 2019-2020 is a valley, we can estimate that the local industry as a whole loses on average more than USD 20M per year because of both concepts.

# Software currently in use

The problem described is not new in the industry. In fact, it surely is as old as the industry itself. And just as in many other economical activities, advances in Information Technologies have been used to improve management for at least 50 years with the introduction of revolutionary systems such as MRP, then MRPII and finally ERP.

These systems have, broadly speaking, the right functionality required to manage the operation, but despite this they tend to fail in the implementation due to a phenomenon called GIGO, for its acronym in "Garbage-In Garbage-Out". This phenomenon, listed as the first problem in the [Wikipedia article](https://en.wikipedia.org/wiki/Material_requirements_planning#Problems_with_MRP_systems){:target="_blank"} on MRP, simply indicates that feeding erroneous information into a system will result in erroneous output.

Where do the errors in the input information come from? From multiple sources of various natures. The following list shows some of them:
Errors in bills of materials (BOM): especially at the beginning of the life-cycle of products, when engineering changes are frequent and urgent. These engineering changes must not only be applied correctly, they must also be applied in sync with the first batch that requires them.
Incongruences between the products planned and the products actually produced: oftentimes products in the catalog can have slightly differing models, with variations in some parts or subassemblies, but sharing others.
Failure to detect process scrap and missing parts caused by supplier errors: especially in automated insertion processes such as SMT or THT, in which suppliers often fraction reels of components with little care or neglecting the need of extra tape for splicing.
Undetected supplier errors in the consolidation of kits: some suppliers choose not to fraction reels (due to what is expressed in the previous point), and instead send excess material in early shipments only to discount them later in subsequent lots. This forces the operation to monitor excess material for each part number and ensure the balance is always positive, taking into account that these components might be used in several different products, affected by engineering changes, etc. It is common for suppliers to make mistakes in this management, and factories often fail to detect them.
Subassembly counting errors during production: due to manual or semi-automatic counting (counted by ad-hoc systems such as shopfloor) and then fed to the MRP manually or automatically but requiring supervision and/or human intervention

These errors, once entered into the systems, are difficult to accurately quantify and therefore impossible to subsequently correct without resorting to physical inventory taking. As a result, errors accumulate over time and end up being detected in production, especially at the end of a production run. Surprise detection brings with it a huge impact on the use of labor, and if it occurs towards the end of the life-cycle of a product, it also limits the possibility of replacement of many exclusive parts, thus causing obsolescence.

All these errors can be mitigated to some extent by developing robust processes, but they can hardly be eliminated at a reasonable cost only through good practices. As in many other aspects of manufacturing, we must be content with partial controls, on representative samples, to obtain a favorable cost / benefit ratio.

The reason why these systems fail to capture the reality of the production floor lies in that they were conceived to work at the business level, executing complex rules and multiple calculations (especially ERP), with a relatively low transaction capacity. This forces the information to be captured using other tools (manual or automated) and then feeding said information in a delayed way (possibly at the end of each day). The ANSI / ISA-95 standard defines the following software “levels” within the computerization of the business:

![ISA 95 Software Levels](/assets/image1.png)

As can be seen in the [figure](https://www.researchgate.net/figure/The-automation-pyramid-according-to-the-ISA-95-model-The-five-levels-0-5-are-defined_fig2_326224890){:target="_blank"}, ERP-type systems are located at level 4. Levels 2, 1 and 0 contain the software that runs on the manufacturing equipment, and level 3 contains a kind of system known as MES (Manufacturing Execution System). The latter (MES), unlike MRP / ERP, are poorly standardized, with each vendor offering different features depending on the specific target industry. It is also common for manufacturing companies to develop their own software to perform these functions in the absence of clearly suitable alternatives. This has the advantage of the flexibility of in-house development, but at an enormous cost of creation and maintenance in an activity (software development) that is usually outside the technical expertise of manufacturing organizations.

Regardless of the specific solution used, the main problem arises from inaccuracies and delays in data capture and entry. And because the information in the systems is usually at least one day old, it is impossible to contrast it against physical reality (at least without resorting to expensive WIP flushing).

# New computing paradigms

Both MRP / ERP and MES systems have origins that go back several decades in the past, and although conceptually nothing has changed, Information Technologies have made enormous advances, both in software and hardware.

These advances have not only been technical, but also economic. The development and proliferation of open source tools [FOSS (Free and Open-Source Software)](https://en.wikipedia.org/wiki/Free_and_open-source_software){:target="_blank"} open up a world of possibilities for technological innovation. This movement has produced technological wonders ranging from small computers with modern connectivity for around USD50 ([Raspberry Pi](https://www.raspberrypi.org/){:target="_blank"} and the like), operating systems ([Linux](https://www.linux.org/){:target="_blank"}), databases with features and performance comparable to the traditional giants ([PostgreSQL](https://www.postgresql.org/){:target="_blank"}), simulation tools ([SimPy](https://simpy.readthedocs.io/en/latest/){:target="_blank"}) and optimization tools ([Google OR Tools](https://developers.google.com/optimization){:target="_blank"}), among many, many others. In contrast, access to these types of tools before the advent of open source software could cost in the hundreds of thousands of dollars.

This combination of hardware and software at unprecedented costs, added to the explosion of digital communications, gave rise to new paradigms in the implementation of software systems "in the cloud", such as [SaaS (Software as a Service)](https://en.wikipedia.org/wiki/Software_as_a_service){:target="_blank"}. This in turn gives both software vendors and end users access to high quality informatization, with very low acquisition and maintenance costs.

How does this affect the problems described? By enabling the implementation of highly connected systems, capable of running critical business functions in real time, allowing the detection of errors instantly, at affordable costs.

“Real time” is the key here, since it allows for the immediate inspection of the physical versus logical inventory at any point in the operation, without the need to interrupt the operation. In addition, by knowing the logical status of the inventory live, it is possible to dispatch materials to the line Just-In-Time, with only a few minutes in advance to allow a smooth operation. In case of physical inventory shortages (due to undeclared scrap or supplier errors), the detection is immediate at the time of replenishment: the material is physically exhausted but the system will not issue the replenishment because the logical stock does not require it. Once the shortage is identified, it can be fed into the system so that it will issue a replenishment. And since the MRP function runs live, it is possible to see the future impact of the shortage immediately, and take corresponding actions.

This same real-time feature allows the analysis of production flows, stops, speed losses, and other deviations from expected cycle times as they occur, station by station, line by line, giving enormous visibility to problems and enabling its prompt engagement.

And lastly, with a system quick enough to process hundreds of transactions per second, it’s possible to easily create discrete event simulations in order to analyze different planning scenarios utilizing the labor in different ways.




<!-- You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/ -->
