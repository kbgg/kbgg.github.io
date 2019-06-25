---
layout: post
title:  "QGIS STAC Browser: Past, Present, and Future"
date:   2019-06-26
categories: blog 
---

> The SpatioTemporal Asset Catalog (STAC) specification provides a common language to describe a range of geospatial information, so it can more easily be indexed and discovered. 
> A 'spatiotemporal asset' is any file that represents information about the earth captured in a certain space and time. 

*- [SpatioTemporal Asset Catalog Specification](https://stacspec.org)*

## Past

Earlier this year I started looking for ways to download large quantities of Landsat scenes for my thesis research.
Ideally, there would be an API I could utilize to search for scenes which are within my study areas and study periods.
I quickly found out that such an API doesn't exist and my only alternative would be to write a script to interact with the [EarthExplorer](https://earthexplorer.usgs.gov/) site (far from ideal).


At first I conceded defeat but then I ran into one of [Chris Holmes'](https://twitter.com/opencholmes) [blog posts](https://medium.com/radiant-earth-insights/the-potential-of-spatiotemporal-asset-catalogs-a9323927dc8a) describing work on a new specification called SpatioTemporal Asset Catalogs.
Immediately I saw the incredible potential in standardizing the way we access spatiotemporal assets.
Imagine being an imagery provider and not having to spend time reinventing the wheel when you want open access to your imagery.
Imagine not having to learn how to navigate a new website for every different source of imagery you want to access.
Imagine being able to automate analysis by building pipelines on top of a standard API.
The possibilities this standard enables really change the way we do geospatial analysis.


I jumped right in and started learning about the spec and introuced myself to the community.
At the time I joined in there was a lot of progress on static catalogs and work on the dynamic catalog API was starting to mature.
There was one thing that hadn't really been worked on yet and that was tools to interact with the dynamic catalog APIs and download assets.
I asked around and there wasn't a QGIS plugin started yet so I got to work.

## Present

My goal for the QGIS plugin is to have an EarthExplorer-like experience but instead of only being able to search for assets from one provider (USGS in the case of EarthExplorer), you can search and download assets from any provider which provides a STAC API.
I just released version 1.0.0 of the [plugin](https://plugins.qgis.org/plugins/stac_browser/) which has just enough functionality to do the basic tasks: search for and download assets.
Although the functionality is very basic it already creates a much better user experience than traditional interfaces.
Below are some comparisons of the flow for searching for and downloading a truecolor Landsat image for a study area in EarthExplorer and in the QGIS STAC Browser plugin.

### EarthExplorer (2 Minutes and 52 Seconds)
<video width="100%" controls autoplay loop>
	<source src="/assets/stac/comparison_ee.mp4" type="video/mp4">
    Video could not be loaded
</video>
### QGIS STAC Browser (37 Seconds)
<video width="100%" controls autoplay loop>
	<source src="/assets/stac/comparison_stac.mp4" type="video/mp4">
    Video could not be loaded
</video>
## Future

There's still a lot of work to be done on this project.
Below is an incomplete list of just a few things which I'd like to get added to the plugin.

* Add filtering of scenes based on properties
* Allow adding APIs which require some sort of authentication
* Create a better experience for selecting bands/assets to download
* Add unit testing to the codebase
* Create documentation

If you have any suggestions for new features or find any bugs please create an issue on our [github](https://github.com/kbgg/qgis-stac-browser).
I'm also always looking for new contributors so if you'd like to get started just shoot me an email at [kevin@kb.gg](mailto:kevin@kb.gg).
I'm looking forward to seeing all the cool things everyone does with this plugin!


\- Kevin
