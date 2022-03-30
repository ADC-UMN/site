# Website

Made with Hugo with the Syna theme.

This is the repository containing the markdown files, Hugo configurations, and deploy shell script. For the hosted HTML, CSS, and JS, see [the other repository](https://github.com/ADC-UMN/ADC-UMN.github.io)

## How to update

1. Clone this repository

```bash
git clone https://github.com/ADC-UMN/site.git
```

2. Test the website out locally

```bash
cd site
hugo server # see http://localhost:1313 in your browser
# Ctrl + C to kill the server
```

3. Remove the `public` directory

```bash
rm -rf public
```

4. Create a git [submodule](https://github.com/blog/2104-working-with-submodules)

```bash
git submodule add -b master https://github.com/ADC-UMN/ADC-UMN.github.io.git public
```

Now when you run the `hugo` command to build the site to `public`, the created `public` directory will have the aforementioned other repository as its remote origin instead of this repository.

4. Make changes to the content

Focus on the `content` directory, which has the markdown files for the site. It has this structure:

```bash
content/
+--_global/ # appears on every page
|  +--copyright.md
|  +--footer.md
|  +--index.md
|  +--nav.md # top navigation bar
+--_index/ # content for the main page at '/'
|  +--about/ # about section
|  |  +--content.md
|  |  +--index.md
|  +--coding/ # coding section
|  |  +--index.md
|  +--hero/ # hero immediately below the navigation bar with the buttons and particle effects
|  |  +--config.json
|  |  +--index.md
|  +--network/ # network section
|  |  +--index.md
|  +--speakers/ # speakers section
|  |  +--index.md
|  +--index.md
+--board/ # content for the page at '/board'
|  +--_index/
|  |  +--name1.md
|  |  +--name2.md
...
|  +--index.md
+--meetings/ # content for the page at '/meetings'
|  +--_index/
|  |  +--fall.md # fall semester event calendar as a table
|  |  +--index.md
|  |  +--spring.md # spring semester event calendar as a table
|  +--index.md
+--_index.md
```

5. Commit and push changes

```bash
git add .
git commit -m 'a descriptive message'
git push
```

6. Run the deploy script

```bash
./deploy.sh 'a descriptive message'
```