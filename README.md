# How to build a Phoenix hello world rest API

Recently I went to a
[Meetup](https://www.meetup.com/Elixir-Mexico-City/events/238410497/) on Mexico
City about Elixir, after all the introduction made by [Norberto
Ortigoza](https://medium.com/@hiphoox), I got impressed about all the
expressiveness of the language, their concurrent capacity and how it meets
current web development state of art.

I got a lot of inspiration from that event, so I decided to give it a try for
one our most common use case at [Yalo](https://medium.com/@Yalochat), a Rest API
microservice. Many of the articles I found about rendering pure JSON are not up
to date and most of them include html views render. So I decided to write this
article for my own log and to help others that probably are my current
situation.

#### Requirements

* Elixir > 1.4 and Phoenix running

#### Generate the new Phoenix application

First we will generate a new Phoenix application that doesn’t include html
assets and database.

    $ mix phoenix.new hello_phoenix_api --no-brunch --no-ecto

You should see and output like this.

![](https://cdn-images-1.medium.com/max/720/1*7HhgWcCQznyPF82zdBi_Kg.png)
<span class="figcaption_hack">new Phoenix app scaffold</span>

Be sure to install all dependencies typing 

![](https://cdn-images-1.medium.com/max/720/1*T-6z-cTQ5ePuCfvyjBbIPA.png)

#### Create the route, controller and view

After the new project generation we’re going to create the route for our hello
world endpoint. Open the file  . The file should look like this:

We’re going to remove the  scope,  pipeline and use the root path to render our
json payload, the file should be as follow:

Now run  to start your application and open your browser on  and you should see
an error page like this:

![](https://cdn-images-1.medium.com/max/900/1*oGLAMidqvPFMAfsiqgNY3Q.png)

It means that you don’t have the appropriate controller that maps to the route.

Remove the  file because you don’t need it any more.

Now create your controller file at  with the following content:

Run phoenix server again and you should see this response:

![](https://cdn-images-1.medium.com/max/900/1*o1ILA80ZDa1quCVZVw95uA.png)

Now is time to create the view, in 

After you go to  again and refresh the page you will see how the view render a
json response

![](https://cdn-images-1.medium.com/max/720/1*PbHPX8AFb_reswocC1h1Mg.png)

Let me know if this is usefull for you or if I have any errors.

#### Unit testing

Now lets add a simple unit test to our REST endpoint. First you need to add the
[Poison](https://github.com/devinus/poison) library which allows to parse JSON
objects into maps. Add to your  file into the deps list and download the
dependency by typing  in your terminal.

![](https://cdn-images-1.medium.com/max/720/1*f1wGbbSpiRpKZ435n3wRFg.png)

Create the file  with the following content:

Run your test from the terminal with  you’ll see an output like this:

![](https://cdn-images-1.medium.com/max/720/1*YEXY1YKEJ8AJy43VKZXgKw.png)

> fred

* [Elixir](https://medium.com/tag/elixir?source=post)
* [Phoenix](https://medium.com/tag/phoenix?source=post)

### [Fred Allen](https://medium.com/@fredjourney)

Developer and community enthusiast
