---
date: 2020-10-10 12:26:40
layout: post
title: 4 Tips for Creating Accessible Qlik Sense Mashups
description: Qlik has made every effort to keep Qlik Sense in line with the latest trends and most advanced technologies, and the same goes for making the analytics tool accessible to people with disabilities.
image: https://www.clusterdesign.com.br/wp-content/uploads/2019/09/qlik-sense-acessibility-2.jpg
optimized_image: https://www.clusterdesign.com.br/wp-content/uploads/2019/09/qlik-sense-acessibility-2.jpg
category: mashup
tags:
    - mashup
    - javascript
    - css
author: thomaspessato
---

Native Qlik Sense apps currently support the JAWS screen reader, as well as compatibility with Internet Explorer 11. However, the best way to engage and combine the power of Qlik Sense with accessible web application development standards is via mashup implementations that render the web experience more enjoyable and truly ready to use for people with disabilities, especially people who need screen readers or who can’t use a mouse or keyboard to navigate.

When we engage web languages and embed graphics or even customize them we gain the ability to design user interfaces that are compatible with free desktop screen readers such as NVDA, or ready to use in the palm of your hand through native Android and iOS screen readers.

## Customized experience when using Mashups

A mashup provides much more freedom and flexibility to create an application that fits the specific needs of each user group. Whether creating a custom filter menu or adding dynamically accessible properties and attributes, the focus of an accessible mashup is to create an intuitive layout with smooth mouse and keyboard navigation.

### Native Qlik Sense QVF limitations and how mashup engagement overcomes such limitations

When developing a web application with screen readers in mind, one important thing to keep in mind is make sure the user remains always aware of what is happening and where the focus is on the screen.

In the native application, the navigation works apparently well. But when using the NVDA reader, focusing on a table-like object, for example, the user receives no feedback with regards to what object is being focused on, since the table’s title is not read. This is something that can be solved in a mashup using the aria-label HTML attribute.

Engaging mashups we can, for example, help the user navigate information, control focus on screen elements, change text and element captions based on user actions, and create predictable QVF functionality components that have a simple and natural use.

## 4 quick tips for making an accessible mashups

### 1 – Help the user navigate

A good example is to create a “skip to main content” button at the top of the page that is hidden by default, but that becomes visible when it gets a keyboard focus.

### 2 – Make the user aware of what is happening on the screen

If you have a loading screen or an error screen, be sure to add focus to some text that tells the user that the application is loading or that an error has occurred. Example:


![placeholder](https://www.clusterdesign.com.br/wp-content/uploads/2019/09/F921D729-5658-4404-902B-0385A9F90AD7.png-1-300x246.jpg 'Image loading with a text attached')

### 3 – Always remember to test your mashup in other platforms

Sometimes some solutions that make the application more accessible work slightly differently on different platforms. It is therefore important to always make sure that we are achieving the expected behaviour on all platforms. Otherwise you will need to find another way to reach the expected goal.

### 4 - Less is more

Get rid of absolutely everything your user won’t use in the interface. For example, the native app’s edit bar, where users can edit and create their graphics and sheets, and so many other elements that we’ve just added to the interface that will eventually make the experience exhausting in areas of little or no importance.
