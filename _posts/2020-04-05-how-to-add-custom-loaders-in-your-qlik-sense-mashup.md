---
date: 2020-04-05 12:26:40
layout: post
title: How to Add Custom Loaders in your Qlik Sense Mashups
description: In some cases, it becomes necessary to have users wait some time while some retrieved data or a webpage is loaded on the screen. Even if this process is relatively fast, it is important to keep the user informed of what is happening on the page while content is rendered.
image: https://www.clusterdesign.com.br/wp-content/uploads/2020/04/loaders-qliksense-mashups.jpg
optimized_image: https://www.clusterdesign.com.br/wp-content/uploads/2020/04/loaders-qliksense-mashups.jpg
category: react
tags:
    - react
    - javascript
    - css
author: caiosuarez
---

In some cases, it becomes necessary to have users wait some time while some retrieved data or a webpage is loaded on the screen. Even if this process is relatively fast, it is important to keep the user informed of what is happening on the page while content is rendered. And that’s when a Loader comes in, a very useful feature that helps users get feedback on the screen while they wait for the indented information to be displayed.

The process of rendering Qlik Sense Data inside a Mashup behaves no differently, and loaders become a useful UX tool at our disposal.

## Situations in which it is a good idea to use a ‘loader’

-   When opening the mashup for the first time (for example while creating the connection between the mashup and qvf)
-   Any time you are loading data for the first time (such as kpis and graphics)

In this post, I’ll show you a brief tutorial on how to add a loader to your Qlik Sense Mashup, yielding a result like the one shown below:

![placeholder](https://clusterdesign.com.br/wp-content/uploads/2020/04/loader.gif 'Large example image')

## Requirements

-   A Mashup with an active connection to a QVF
-   A Text editor (I use Visual Studio Code)
-   Knowledge in HTML, JS and React JS (I programmed this example in ReactJS, but you can adapt it to another framework, if you prefer)

## Tutorial

The first step is to define what our Loader will look like. In this example, we will select one from an open-source collection at the following site: https://tobiasahlin.com/spinkit/

After choosing one, click on the “Source” button at the top of the page and copy the HTML code.

![placeholder](https://www.clusterdesign.com.br/wp-content/uploads/2020/04/loader-img.jpg 'Large example image')
![placeholder](https://www.clusterdesign.com.br/wp-content/uploads/2020/04/html-loader.jpg 'Large example image')
<em>Note: do not close the page yet as we will then copy the CSS.</em>

With the copied HTML, we can now create our Loader component, which will look something like this:

## Code

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus.

```js
class Loader extends React.Component {
	constructor(props) {
		super(props);
		this.state = {};
	}

	render() {
		let style = {
			height: 'calc(100vh - 63px)',
			display: 'flex',
			alignItems: 'center',
			justifyContent: 'center',
		};
		return (
			<div style={style}>
				<div class="spinner">
					<div class="cube1"></div>
					<div class="cube1"></div>
				</div>
			</div>
		);
	}
}
```

Do not forget to add the loader’s CSS code, which will give it movement, define it’s colors, size and other visual properties. To do this, go back to the page where we copied the HTML from, proceed to copy the CSS, and finally paste it into your Mashup’s CSS file.

![placeholder](https://www.clusterdesign.com.br/wp-content/uploads/2020/04/loader-css.jpg 'Large example image')

Done! Our Loader component is ready. Now you just need to identify what situations are suited to render it on the screen.

The first case to do so, is when the Mashup is making the first connection to QVF, but when the connection is not yet complete; as shown in the following example:

The App.js file is the first Javascript file to be read in my application. As such, this is the place where I instantiate the QlikConnection component that creates the entire connection and returns the Qlik module via the callback property (line 68). Therefore, it is possible to know whether the loader should be displayed or not via the callback.

In your application you should have something similar, so just apply the same concept.

![placeholder](https://www.clusterdesign.com.br/wp-content/uploads/2020/04/app.js.jpg 'Large example image')

In this case I defined a variable called “page” that initially points to the Component Loader that we created (line 48) and is rendered when the file is returned (line 67). This ensures the first thing that will be displayed on the screen when we open the application is our Loader. On line 51, we check to see if the QlikConnection component has finished connecting to the QVF. As soon as the mashup is connected to QVF, the variable page stops pointing to the Loader Component and starts pointing to the page Component that will be drawn on the screen.

Now whenever we open our Mashup, this loader will appear until the connection to the QVF is made.

## Final Remarks

Following the same logic, you can also create a range of loaders for individual objects. Instead of calling the Loader Component inside the App.js file, you should do it within the desired Object Component where the loader will be displayed while there is no data yet to be displayed.

Remember that you can also customize this loader’s CSS, or if you prefer you can also use loaders from other libraries or even in other formats, such as GIFs or SVGs.

<strong>If you need to develop advanced features for Qlik Sense through mashups or extensions, send us an email: info@clusterdesign.com.br</strong>
