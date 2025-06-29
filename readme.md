# Code For Dayton Website

This is a pretty standard [Jekyll](https://jekyllrb.com/) website at http://www.codefordayton.org/; there are a number of datasets in `_data` that build various lists displayed on the site. This site was **heavily** based on the website for [Code For Boston](https://www.codeforboston.org/).

Please be sure to read our [Code of Conduct](http://www.codefordayton.org/code-of-conduct/). CFD is a local civic hacking group aligned with the [Alliance of Civic Technologists (ACT)](https://www.civictechnologists.org/).

## I want to build the website locally. How do I do that?

- Ensure you have Ruby installed on your system and available from your system `$PATH`. Instructions will vary per environment but are available [here](https://www.ruby-lang.org/en/documentation/installation/).

```
$> ruby --version
ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-linux]
```

- (Optional, only for those looking to contribute changes upstream) Ensure you have Git installed on your system and available from your system `$PATH`. Instructions will vary per environment but are available [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

```
$> $ git --version
git version 2.17.1
```

- Install [Jekyll](https://jekyllrb.com/) through Ruby's [Gem](https://rubygems.org/) package management system. Jekyll is a dynamic website generator that allows Ruby code to be executed at build time. The result is a site of static pages.

```
$> gem install jekyll jekyll-redirect-from
Building native extensions. This could take a while...
...lots of output...
21 gems installed
```

- NOTE: When the Jekyll gem is installed it will rely on several native dependencies on your system, and you may have to go hunting to find these. For instance, on Fedora 27, you may need to install `gcc-c++`, `redhat-rpm-config`, and `ruby-devel` using a command like:

```
$> sudo dnf install gcc-c++ redhat-rpm-config ruby-devel
```

- Fork the upstream code repository at [https://github.com/codefordayton/codefordayton.org](https://github.com/codefordayton/codefordayton.org) into your namespace using the GitHub UI.

- Clone your namespace's remote into your local file system. Copy the address of your remote repository, then use that as an argument to the `git clone` command. For those not using `git`, simply download the sources using GitHub's UI. In the command below, remember to replace `ALRubinger` with your GitHub user name.

```
$> git clone git@github.com:DavidEBest/codefordayton.org.git
Cloning into 'codefordayton.org'...
remote: Counting objects: 1739, done.
Receiving objects:  24% (418/1739), 1.65 MiB | 3.23 MiB
...a lot of output...
Resolving deltas: 100% (867/867), done.
```

- Move into the new working directory

```
$> cd codefordayton.org
```

- Add a reference to the upstream remote repository so that you may later synchronize changes with new work.

```
$> git remote add upstream git@github.com:codefordayton/codefordayton.org.git
```

- Use Jekyll to build the site!

```
$> $ jekyll build
```

- Use Jekyll to start a small local web server to serve the site, reloading the build with changes you make to local files

```
$> $ jekyll serve --livereload
...lots of output...
LiveReload address: http://127.0.0.1:35729
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

- View the site using your web browser at the address indicated above, in this case `http://127.0.0.1:4000/`. Changes you make to the source files should trigger a Jekyll rebuild and appear in your browser once done.

## I want to update the wesite. How do I do that?

- To add/update events, edit [`_data/events/active.yml`](https://github.com/codefordayton/codefordayton.org/edit/main/_data/events/active.yml)
- To add/update current projects, edit [`_data/projects/active.yml`](https://github.com/codefordayton/codefordayton.org/edit/main/_data/projects/active.yml)
- To add/update retired projects, edit [`_data/projects/inactive.yml`](https://github.com/codefordayton/codefordayton.org/edit/main/_data/projects/inactive.yml)
- To edit normal site pages, edit the `html` or `markdown` files in `_pages/`
- To edit the homepage content, edit `index.html`

## Deploy to codefordayton.org

This site is hosted via [GitHub Pages](https://pages.github.com/), so all you need to do to deploy is to push updates to the `main` branch in GitHub. Within minutes, http://www.codefordayton.org/ will reflect the new changes.
