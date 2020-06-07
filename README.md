<p align="center">
  <img src="https://raw.githubusercontent.com/slatedocs/img/master/logo-slate.png" alt="Slate: API Documentation Generator" width="226">
  <br>
  <a href="https://github.com/slatedocs/slate/actions?query=workflow%3ABuild+branch%3Amaster"><img src="https://github.com/slatedocs/slate/workflows/Build/badge.svg?branch=master" alt="Build Status"></a>
</p>

<p align="center">Slate helps you create beautiful, intelligent, responsive API documentation.</p>

<p align="center"><img src="https://raw.githubusercontent.com/slatedocs/img/master/screenshot-slate.png" width=700 alt="Screenshot of Example Documentation created with Slate"></p>

<p align="center"><em>The example above was created with Slate. Check it out at <a href="https://slatedocs.github.io/slate">slatedocs.github.io/slate</a>.</em></p>

Features
------------

* **Clean, intuitive design** — With Slate, the description of your API is on the left side of your documentation, and all the code examples are on the right side. Inspired by [Stripe's](https://stripe.com/docs/api) and [PayPal's](https://developer.paypal.com/webapps/developer/docs/api/) API docs. Slate is responsive, so it looks great on tablets, phones, and even in print.

* **Everything on a single page** — Gone are the days when your users had to search through a million pages to find what they wanted. Slate puts the entire documentation on a single page. We haven't sacrificed linkability, though. As you scroll, your browser's hash will update to the nearest header, so linking to a particular point in the documentation is still natural and easy.

* **Slate is just Markdown** — When you write docs with Slate, you're just writing Markdown, which makes it simple to edit and understand. Everything is written in Markdown — even the code samples are just Markdown code blocks.

* **Write code samples in multiple languages** — If your API has bindings in multiple programming languages, you can easily put in tabs to switch between them. In your document, you'll distinguish different languages by specifying the language name at the top of each code block, just like with GitHub Flavored Markdown.

* **Out-of-the-box syntax highlighting** for [over 100 languages](https://github.com/jneen/rouge/wiki/List-of-supported-languages-and-lexers), no configuration required.

* **Automatic, smoothly scrolling table of contents** on the far left of the page. As you scroll, it displays your current position in the document. It's fast, too. We're using Slate at TripIt to build documentation for our new API, where our table of contents has over 180 entries. We've made sure that the performance remains excellent, even for larger documents.

* **Let your users update your documentation for you** — By default, your Slate-generated documentation is hosted in a public GitHub repository. Not only does this mean you get free hosting for your docs with GitHub Pages, but it also makes it simple for other developers to make pull requests to your docs if they find typos or other problems. Of course, if you don't want to use GitHub, you're also welcome to host your docs elsewhere.

* **RTL Support** Full right-to-left layout for RTL languages such as Arabic, Persian (Farsi), Hebrew etc.

Getting started with Slate is super easy! Simply press the green "use this template" button above and follow the instructions below. Or, if you'd like to check out what Slate is capable of, take a look at the [sample docs](https://slatedocs.github.io/slate/).

Getting Started with Slate
------------------------------

To get started with Slate, please check out the [Getting Started](https://github.com/slatedocs/slate/wiki#getting-started)
section in our [wiki](https://github.com/slatedocs/slate/wiki).

We support running Slate in three different ways:
* [Natively](https://github.com/slatedocs/slate/wiki/Using-Slate-Natively)
* [Using Vagrant](https://github.com/slatedocs/slate/wiki/Using-Slate-in-Vagrant)
* [Using Docker](https://github.com/slatedocs/slate/wiki/Using-Slate-in-Docker)

Provided in the slate repo is a Dockerfile you can use to run slate using [Docker](https://www.docker.com/). Docker is similar to Vagrant in that it provides a reproducible, portable development environment using virtualization, however it does not provide a full VM, rather piggy backing off the host, allowing for a slimmer installation profile than Vagrant / full VMs. However, Docker does come with a number of its own terms, and for beginners, we recommend looking at
[this Glossary](https://docs.microsoft.com/en-us/dotnet/architecture/microservices/container-docker-introduction/docker-terminology)
to familiarize yourself with some of them.

## Dependencies

* [Docker](https://www.docker.com/), see [this page](https://www.docker.com/get-started) for installing Docker Desktop.

## Getting Started

1. Fork this repository on Github.
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/slate.git`
3. `cd slate`
4. Build the docker image for slate: `docker build . -t slate`

## Running Slate

To start a container for slate, run:

```
docker run -d --rm --name slate -p 4567:4567 -v $(pwd)/build:/srv/slate/build -v $(pwd)/source:/srv/slate/source slate
```

and you will be able to access your site at http://localhost:4567.

To build your sources while the container is running, run:

```
docker exec -it slate /bin/bash -c "bundle exec middleman build"
```

## Stopping Slate

To stop the slate container, run:

```bash
docker stop slate
```

## What Now?

The next step is to [learn how to edit `source/index.md` to change the content of your docs](Markdown-Syntax). Once your done, you might want to think about [deploying your docs](https://github.com/slatedocs/slate/wiki/Deploying-Slate).
