# Morphous

Morphous is an extension of Orchard CMS and adds REST API support for Orchard's content management system.

You can use Orchard content items as JSON in mobile or desktop applications, AngularJS or any other type of client.

### Resources
Morphous demo in the 17/05/16 Orchard weekly meeting. This gives the best insight into the core Orchard changes and how Morphous works behind the scenes. 
https://youtu.be/u7S492xr-5s?t=39m19s

The sylapse.com blog posts provide a practical example of creating an Orchard website with Morphous API and a Xamarin mobile app for viewing the contents of the website on iOS or Android.
http://www.sylapse.com/

### Shapes
Shapes are Orchard's ViewModels and Orchard is great at turning them into HTML. All we've done is introduce a way to turn them into JSON as well. These changes sit inside the normal Orchard shape rendering pipeline so all the existing Orchard concepts are still respected. DisplayType (detail/summary) works. So does placement.info, you can Match based on a particular output format so you can add or remove information from your API independently from your website while still using the same content.

## Morphous.Orchard (this repository)
Morphous is modular so you can choose the bits you want. The one bit you will definitely need is our modified version of Orchard which is forked from, and kept up to date with, the official repository. It just contains some small changes to the DisplayManagement process in the Orchard.Framework project. This is where we introduce the idea of ShapeType, so it's possible to write Shape methods that do something other than returning HTML.

## Morphous.Api (includes instructions for getting started) [link](https://github.com/Morphous/Morphous.Api)
To get a content item as JSON you just need to hit the right URL. Morphous.Api contains an ApiController that returns your content items as JSON. It also contains Shape methods like the ones in the normal Orchard.Core project. The difference is that these ones help to build up a model to serialize, instead of returning HTML.

## Morphous.AsyncTemplates [link](https://github.com/Morphous/Morphous.AsyncTemplates)
Some simple templates for Orchard's built in parts and fields that use Angular to display content items returned by the API. Because loading data asynchronously is better than a full page refresh!

## Morphous.TokenAuth [link](https://github.com/Morphous/Morphous.TokenAuth)
Want to authenticate with your Orchard site from an application outside of a web browser? Use this module to allow your Orchard users to sign into their accounts using OAuth2 token authentication, no cookies required.
