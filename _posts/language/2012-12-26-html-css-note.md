---
layout: post
title: "实例学HTML&&CSS"
category: language
tags: [language]
description: |
  HyperText Markup Language (HTML) is the main markup language for displaying web pages and other information that can be displayed in a web browser. 
---
{% include JB/setup %}

[实例学HTML&&CSS](http://liufei.name/language/html-css-note.html)

##1.
<!DOCTYPE html>
<strong>Hello, This is my first write html code.</strong>
output:
Hello, This is my first write html code.

HTML stands for HyperText Markup Language. Hypertext means "text with links in it." Any time you click on a word that brings you to a new webpage, you've clicked on hypertext!

A markup language is a programming language used to make text do more than just sit on a page: it can turn text into images, links, tables, lists, and much more. HTML is the markup language we'll be learning.

What makes webpages pretty? That's CSS—**Cascading Style Sheets**. Think of it like skin and makeup that covers the bones of HTML. We'll learn HTML first, then worry about CSS in later courses.

##2.
<!DOCTYPE html>
<html>
Hello, World!
</html>
In HTML, the order you put things in matters! But formatting (*i.e.* empty space) doesn't matter from a technical point of view.

You will notice there's a pattern in how we indent each line of HTML, though. This is to aid readability and help us catch mistakes. We'll talk more about indentation later!

 
##3.
Feel free to peek back at earlier exercises if you forget exactly what a tag looks like.

##4.
There are always two parts to the file: the head and body. Let's focus on the head.
a. It has an opening and a closing tag.
b. The head includes important information about the webpage, such as its title.
c. The title is the words we see in the tab (for example, the title of this page is "Introduction to HTML").
<!DOCTYPE html>
<html>
<head><title>Hello</title></head>
</html>

##5.
<p></p> paragraphs
<h1></h>
<h2></h>......<h3><h4><h5><h6>
<img src="http://bit.ly/SJxLUx" />
<a href="http://www.codecademy.com">HI clike me!</a>
<a href="http://www.codecademy.com"><img src="http://bit.ly/SJxLUx" /></a>

##6.  
indentation—that is, the amount each line is spaced in from the margin.

ordered lists:
			<ol>
				<li>raindrops on roses</li>
				<li>whiskas on kittens</li>
				<li>call of duty: modern warfare</li>				
			</ol>

            <ul>
				<li>raindrops on roses
                    <ol>
                        <li>11<li>
                        <li>l2<li>
                    </ol>
                </li>
				<li>whiskas on kittens</li>
				<li>call of duty: modern warfare</li>				
			</ul>

##7.
<p style = "font-size: 20px; color: blue; font-family: Garamond">A truly spectacular paragraph!</p>
<body style = "background-color: brown">
<ol style = "background-color: yellow">
<h3 style = "text-align: center">Favorite Football Teams</h3>
<p>Do you hear the people <strong>sing</strong>?</p>
<p>I am <em>so</em> tired.</p>

##8.
{% highlight html %}
        <table border="1px">
            <thead>
                <tr>
                    <th colspan="2">Famous Monsters by Birth Year</th>
                </tr>
                <tr>
                    <th>Famous Monster</th>
                    <th>Birth Year</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>King Kong</td>
                    <td>1933</td>     
                </tr>
                
                <tr>
                    <td>Dracula</td>
                    <td>1897</td>
                </tr>
                
                <tr>
                    <td>Bride of Frankenstein</td>
                    <td>1935</td>
                </tr>
            </tbody>
        </table>
{% endhighlight %}

##9.
{% highlight html %}
    <html>
    <head>
        <title>Table Time</title>
    </head>
    
    <body>
        
        <table style="border-collapse:collapse;">
            <thead>
                <tr>
                    <th colspan="2">Famous Monsters by Birth Year</th>
                </tr>
                <tr style="border-bottom:1px solid black;">
                    <th style="padding:5px;">Famous Monster</th>
                    <th style="padding:5px;border-left:1px solid black;">Birth Year</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="padding:5px;">King Kong</td>
                    <td style="padding:5px;border-left:1px solid black;">1933</td>     
                </tr>
                
                <tr>
                    <td style="padding:5px;">Dracula</td>
                    <td style="padding:5px;border-left:1px solid black;">1897</td>
                </tr>
                
                <tr>
                    <td style="padding:5px;">Bride of Frankenstein</td>
                    <td style="padding:5px;border-left:1px solid black;">1944</td>
                </tr>
            </tbody>
        </table>
        
    </body>

</html>
{% endhighlight %}

##10.
{% highlight cpp %}
   <html>
	<head>
		<title></title>
	</head>
	<body>
		<p><span style="color:red">This</span>This text is black, except for the word red!</p>
	</body>
</html>

<!DOCTYPE html>
<html>
	<head>
		<title>Ye Olde Fancye Booke</title>
		<link type="text/css" rel="stylesheet" href="stylesheet.css"/>
	</head>
	<body>
		<h3>Ye Olde Storye</h3>
		<p><span>A</span> long time ago there was an intrepid young student who wanted to learn CSS...</p>
	</body>
</html>
p {
	font-family:Garamond;
	font-size:16px;
}

h3 {
	font-family:cursive;
	color:#36648b;
	text-align:center;
}

span {
	color:#cc0000;
	font-size:24px;
} 
{% endhighlight %}

##11.
CSS (which stands for Cascading Style Sheets) is a language used to describe the appearance and formatting of your HTML.

##12.
{% highlight html %}
    <!DOCTYPE html>
<html>
	<head>
		<style>
			p {
				color: purple;
			}
		</style>
		<title>Result</title>
	</head>
	<body>
		<p>Check it out! I'm purple!</p>
	</body>
</html>
{% endhighlight %}

