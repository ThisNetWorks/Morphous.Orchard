# Morphous

Morphous is an extension of Orchard CMS and adds REST API support for Orchard's content management system.

You can get Orchard content items as JSON for use in any client application.

## Morphous.Orchard (this repository)
This modified version of Orchard is required for Morphous.Api to work. It's forked from the official repository and is easily kept up to date by merging in official releases. It just contains some small changes to the DisplayManagement process in the Orchard.Framework project. This is where we introduce the idea of BindingType, so it's possible to write Shape methods that do something other than returning HTML.

## Morphous.Api (includes instructions for getting started) [link](https://github.com/Morphous/Morphous.Api)
Morphous.Api contains an ApiController that returns your content items as JSON. It also contains Shape methods like the ones in the normal Orchard.Core project. The difference is that these ones help to build up a model to serialize, instead of returning HTML.

## Morphous.AsyncTemplates [link](https://github.com/Morphous/Morphous.AsyncTemplates)
Some simple templates for Orchard's built in parts and fields that use Angular to display content items returned by the API. Because loading data asynchronously is better than a full page refresh!

## Morphous.TokenAuth [link](https://github.com/Morphous/Morphous.TokenAuth)
Use this module to allow your Orchard users to sign into their accounts using OAuth2 token authentication, no cookies required.

### Shapes
Shapes are Orchard's ViewModels and Orchard automatically turns them into HTML when you view an Orchard site. Morphous just introduces a way to turn them into JSON as well. These changes sit inside the normal Orchard shape rendering pipeline so all the existing Orchard concepts are still respected. DisplayType (detail/summary) works. So does placement.info, you can Match based on a particular output format so you can add or remove information from your API independently from your website while still using the same content.

### Resources
Morphous demo in the 17/05/16 Orchard weekly meeting. This gives some insight into the core Orchard changes and how Morphous works. 
https://youtu.be/u7S492xr-5s?t=39m19s

The sylapse.com blog posts show a practical example of creating an Orchard website with Morphous API and a Xamarin mobile app for viewing the contents of the website on iOS or Android.
http://www.sylapse.com/
