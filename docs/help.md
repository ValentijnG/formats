
This site is built from source texts and structure information
into a set of [Markdown](fileFormats/markdown.md) files that is processed by
[MkDocs]({{mkdocs}})
into [HTML](fileFormats/html.md) files that can be served by
[GitHub Pages]({{ghpages}}).

The build script,
[`build.py`]({{formats}}/blob/master/build.py)
is included.

## Usage

Run `build.py` from the Terminal as follows:

```sh
python3 build.py make
python3 build.py build
python3 build.py docs
python3 build.py g commitmsg
```

`make` compiles Markdown files from the source files.

`build` does `make` and then generates html files from the Markdown files.

`docs` does `make` and then serves the docs locally and them shows them in your browser.

`g` does `make`, and pushes the whole site to GitHub,
where it will be published under <https://dans-labs.github.io/formats/>.
The repo itself will also be committed and pushed to GitHub.

Replace `commitmsg` by anything that is appropriate as a commit message.



## Explanation

### Source
The source texts are in [Markdown](fileFormats/markdown.md), [YAML](fileFormats/yaml.md), and [Text (plain)](dataTypes/textPlain.md)
They are stored in
[folders]({{formats}}/tree/master/source)
of this repository.

Most files are [Markdown](fileFormats/markdown.md) files containing the verbose text fragments
that are part of the docs for data types, file formats and extensions.

There are a few other files:

file | description
--- | ---
[`help.md`]({{formats}}/blob/master/source/help.md) | help for building this site (this file)
[`index.md`]({{formats}}/blob/master/source/index.md) | home page
[`header.md`]({{formats}}/blob/master/source/header.md) | header for all pages
[`footer.md`]({{formats}}/blob/master/source/footer.md) | footer for all pages
[`data.yaml`]({{formats}}/blob/master/source/data.yaml) | relationships, metadata, links
[`urls.list`]({{formats}}/blob/master/source/urls.list) | list of external urls
[`mkdocsIn.yaml`]({{formats}}/blob/master/source/mkdocsIn.yml) | template for the site config file

### Intermediate

The script [`build.py`]({{formats}}/blob/master/build.py)
is responsible for transforming the source files into a set of [Markdown](fileFormats/markdown.md) files.

This is what happens:

*   The structure file, `data.yaml` is read; it contains the information on how
    the data types, file formats, and extensions hang together.
    For each item in these categories, a key-value set is made.
*   The [Markdown](fileFormats/markdown.md) files in the `source` directory are read, and their content
    is added to the key-value sets they belong to.
*   The `header.md` and `footer.md` files are read.
*   For each item in each category a [Markdown](fileFormats/markdown.md) file is created and filled with 
    all relevant information:
    *   Meta data;
    *   Running text from source files;
    *   Links to `{{wikipedia}}`;
    *   Links to `{{fileinfo}}`;
    *   Other links.
*   A new config file for `mkdocs` is created:
    *   A list with external urls that are referenced from the docs, `urls.list`,
        is added to the config
    *   A navigation structure is computed from the items.

??? abstract "transformations"
    The generated [Markdown](fileFormats/markdown.md) text is subjected to a transformation
    which makes the following replacements:

    *   `[:` *dataType* `]` will be expanded to the display name of that data type,
        linked to its documentation page;
    *   `[=` *fileFormat* `]` will be expanded to the display name of that file format,
        linked to its documentation page;
    *   `[` *.extension* `]` will be expanded to the extension itself,
        linked to its documentation page.

??? caution "urls"
    Many urls that we reference are not persistent, so they need maintenance.
    In order to facilitate the maintenance, all urls
    are mapped to an abbreviation.
    The abbreviations appear in the source docs, but no concrete url appears there.

    So in order to update an url, it is only needed to modify it once in the `urls.list` file,
    then all occurrences that are used in the docs will be generated to the new value.

