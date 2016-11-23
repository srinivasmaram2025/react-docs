---
layout: post
title: getting-started
description: getting started
platform: reactjs
control: navigation drawer
documentation: ug
---

# Getting Started

This section helps to get started with Essential ReactJS Navigation Drawer component.

## Create a Navigation Drawer

Refer the common ReactJS [Getting Started](https://help.syncfusion.com/reactjs/overview) Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use <EJ.NavigationDrawer> syntax to render React NavigationDrawer component. Add required properties to <EJ. NavigationDrawer > tag element.

{% highlight javascript %}

          ReactDOM.render(    
               <EJ.NavigationDrawer id="navpanedefault"
               </EJ.NavigationDrawer>,
               document.getElementById('navigation')
          );

{% endhighlight %}

Define an HTML element for adding Navigation Drawer in the application and refer the JSX file created.

{% highlight html %}

       <div id="navigation"></div> 
       <script type="text/babel" src="sample.jsx">
       
{% endhighlight %}

## Configuring properties

In the JSX, need to declare the navigation drawer properties. Refer to the following code,

{% highlight javascript %}

         ReactDOM.render(    
                <EJ.NavigationDrawer id="navpanedefault" type="overlay" direction="left" enableListView={true} listViewSettings-width={220} listViewSettings-height="100%" 
                listViewSettings-selectedItemIndex="0" position="normal">
                    <ul>
                        <li data-ej-text="Home"></li>
                        <li data-ej-text="People"></li>
                        <li data-ej-text="Profile"></li>
                    </ul>
                </EJ.NavigationDrawer>,
                document.getElementById('navigation')

        );

{% endhighlight %}

Create the target element as follows to display the list items by clicking target icon.

{% highlight html %}

  <div id="targetPane">
    <div className="e-lv">
        <div className="e-header">
            <div id="drawer" className="drawericon e-icon alignText"></div>
        </div>
    </div>
  </div>
  
{% endhighlight %}

To set the target icon image and with the correct position as using the below mentioned styles.

{% highlight css %}

    <style>
    
        .drawericon {
            background-position: center center;
            background-repeat: no-repeat;
            height: 45px;
            width: 32px;
            background-size: 100% 100%;
            padding-right: 10px;
        }

        .drawericon:before {
            content: "\e76b";
            font-size: 24px;
            height: 26px;
            line-height: 24px;
        }

        #targetPane {
            height: 220px;
            position: relative;
            padding: 0px;
            overflow: hidden;
            margin: 0px;
        }

    </style>

{% endhighlight %}

![](Getting-Started_images\getting-started_img1.png)

You can open the list items by clicking on target element using the targetId property. 

{% highlight javascript %}

         ReactDOM.render(    
               <EJ.NavigationDrawer id="navpanedefault" type="overlay" direction="left" targetId="drawer" enableListView={true} listViewSettings-width={220} listViewSettings-height="100%" 
                listViewSettings-selectedItemIndex="0" position="normal">
                    <ul>
                        <li data-ej-text="Home"></li>
                        <li data-ej-text="People"></li>
                        <li data-ej-text="Profile"></li>
                    </ul>
               </EJ.NavigationDrawer>,
               document.getElementById('navigation')
         );

{% endhighlight %}

![](Getting-Started_images\getting-started_img2.png)

To set the images for list items of the Navigation Drawer by using the data-ej-imageclass property as follows.

{% highlight javascript %}

       ReactDOM.render(    
               <EJ.NavigationDrawer id="navpanedefault" type="overlay" direction="left" targetId="drawer" enableListView={true} listViewSettings-width={220} listViewSettings-height="100%" 
                listViewSettings-selectedItemIndex="0" position="normal">
                    <ul>
                        <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>
                        <li data-ej-imageclass="icon-photos" data-ej-text="Photos"></li>
                        <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>
                    </ul>
               </EJ.NavigationDrawer>,
               document.getElementById('navigation')
      );

{% endhighlight %}

To set the images with the correct position by using the mentioned styles.

{% highlight css %}

    <style>
    
       #navpane [class*="icon-"] {
           width: 40px;
           height: 29px;
           background-image: url("http://js.syncfusion.com/ug/web/content/drawer/sprite.png");
       }

       .icon-home {
           background-position: 0 1px;
       }

       .icon-profile {
           background-position: 0px -532px;
       }

       .icon-photos {
           background-position: 0 -140px;
       }
       
    </style>

{% endhighlight %}

![](Getting-Started_images\getting-started_img3.png)

To add desired page content while selecting the options in navigation drawer as follows.

{% highlight html %}

    <!-- Home Page Content-->

    <div id="Home">

        The Home screen allows you to choose the specific content type displayed.

    </div>

    <!-- Profile Page Content-->

    <div id="Profile" style="display: none">

        The Profile page content is displayed.

    </div>

    <!-- Photos Page Content-->

    <div id="Photos" style="display: none">

        The Photos page content is displayed.

    </div>

{% endhighlight %}

To load the appropriate content for the navigation by using the listViewSettings-mouseUp event handler of ListView component.

{% highlight javascript %}

       ReactDOM.render(    
               <EJ.NavigationDrawer id="navpanedefault" type="overlay" direction="left" targetId="drawer" enableListView={true} listViewSettings-width={220} listViewSettings-height="100%" 
                listViewSettings-selectedItemIndex="0" listViewSettings-mouseUp={this.headChange} position="normal">
                    <ul>
                        <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>
                        <li data-ej-imageclass="icon-photos" data-ej-text="Photos"></li>
                        <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>
                    </ul>
               </EJ.NavigationDrawer>,
               document.getElementById('navigation')
      );

{% endhighlight %}

In the mouse, up handler, it’s display the respective selected item’s content.

{% highlight javascript %}

         headChange: function (e) {
              $('#Home, #Profile, #Photos').hide(); //Hiding all other contents
              $('#' + e.text).show(); //Displaying the content based on the text of item selected
          }

{% endhighlight %}

Run the above code to render the following output. 

![](Getting-Started_images\getting-started_img4.png)

## Customize Direction

By using direction property, to change the list view open direction. The possible directions are Right, Left and the Left is default value.

{% highlight javascript %}

     ReactDOM.render(    
         <EJ.NavigationDrawer id="navpanedefault" type="overlay" direction="right" targetId="drawer" enableListView={true} listViewSettings-width={220} listViewSettings-height="100%" 
                listViewSettings-selectedItemIndex="0" listViewSettings-mouseUp={this.headChange} position="normal">
                    <ul>
                        <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>
                        <li data-ej-imageclass="icon-photos" data-ej-text="Photos"></li>
                        <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>
                    </ul>
          </EJ.NavigationDrawer>,
          document.getElementById('navigation')
    );

{% endhighlight %}

![](Getting-Started_images\getting-started_img5.png)

N> To get the complete API list for all the Syncfusion component’s properties from the [API reference](https://help.syncfusion.com/api/js/ejnavigationdrawer)
