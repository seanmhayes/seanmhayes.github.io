---
layout: post
title:  "Controlling an Arduino through a Web Browser"
date:   2015-06-30 16:23:33
categories: hardware
---
In our group we are building a model factory that shows how renewable energy may be used intelligently. In order to control LEDs which indicate the state of various components of our model, we are using an Arduino.

To control the Arduino, we want to use a dashboard based in a web browser. The current version of this dashboard is a very basic html web page, running on a [Wampserver](http://www.wampserver.com/en/2011/11/11/php-formations-en/). Clicking on hyperlinks on the "index.html" webpage sends the desired state of the relevant component to a *.php file specific to that component. The *.php file then sends this state (0, 1, or 2) to a *.txt file where it is stored.

On the machine where the Wampserver is running, a [Processing](https://processing.org/) sketch loops through each of the *.txt files where the component states are stored. The Processing sketch then converts each state to a character, where A indicates component 1 is ON, B indicates component 1 is OFF, C indicates component 2 is ON, etc..

The Processing sketch then sends each active character to the serial monitor of an Arduino connected to the same machine. The sketch on the Arduino listens to the serial monitor, and depending on which characters are being sent to it turns on or off LEDs, or in some cases changes the colour of LEDs.

The Arduino sketch is looping continuously, while the Processing sketch has a delay of 0.1 s between sending each active character to the serial monitor. In this way, with six components, it will be a maximum of 0.6 s before the Arduino gets a chance (for 0.1 s) to recognize a new character on the serial monitor, and act on the components accordingly.

All files relevant to this project are uploaded to GitHub [here](https://github.com/seanmhayes/IERG_FOTF.git).

![Basic Flow Diagram](https://github.com/seanmhayes/seanmhayes.github.io/blob/master/Images/WebsiteCommandFlow.png "Logo Title Text 1")


Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
