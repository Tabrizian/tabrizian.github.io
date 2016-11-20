# Introduction
This is the source code to my personal website built using jekyll. To run 
it using docker do the following:

```sh
git clone https://github.com/tabrizian/tabrizian.github.io
cd tabrizian.github.io
docker run -d -v $(pwd):/srv/jekyll -p 4000:4000 jekyll/jekyll 
```

