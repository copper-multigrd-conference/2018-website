# website

Public website data

# To test:

1. clone: `git clone git@github.com:copper-multigrd-conference/2018-website.git`
2. build: `./make.py`
3. view: the static html pages are built in `live`.  Use `python3 -m http.server 8000` and point your browser to `localhost:8000` to view.
4. sync: rsync the `live` directory to your favorite server

5. To make an archive of the program (i.e., a copy of the program webpages that does not reside on the easy chair website)
    a) make a directory called program-static
    b) invoke the following command

           wget -r --level=0 -E --ignore-length -k -p -erobots=off -np -N -nH --cut-dirs=2 http://easychair.org/smart-program/CM2018/index.html

    c) you might want to put a pointer to this in _index.html
    d) then  tar cvzf blecko.tgz program-static
    e) then untar this where the copper webpages site. Currently, I do
          tar cvzf static.tgz program-static
          scp static.tgz copper@man-bat.colorado.edu:.
          ssh copper@man-bat.colorado.edu
     
          and then 

          cd public_html/2018
          tar xvzf /home/copper/static.tgz 


# Requirements

The data is stored with `yaml`.

The pages are generated with `jinja2`.

# Notes:

- bootstrap is v4 from branch `v4-dev`
- to retrieve program: `
wget -r --level=0 -E --ignore-length -k -p -erobots=off -np -N -nH --cut-dirs=2 http://easychair.org/smart-program/CM2018/index.html
- from last year, copy repo, update `bootstrap` and `font-awesome`.  Fix and go.
- updates needed:
     ** easychair links
     ** copper lift ticket info
     ** data files
     ** groupcode

