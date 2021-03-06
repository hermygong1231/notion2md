# Notion Markdown Exporter
[![PyPI version](https://badge.fury.io/py/notion2md.svg)](https://badge.fury.io/py/notion2md)

- This is Notion Markdown Exporter using [`notion-py`](https://github.com/jamalex/notion-py)

- **notion2md** will export your [notion.so](http://notion.so) page to markdown formatted file.

### Caution

- Do not share your `Token_v2` with others. Others can access your notion page if the token is shared.

## Features

- [**New**] Token_v2 will be saved after using the exporter, and don't have to enter it next time

- Converts **almost every block** in the notion's page to Markdown texts

- Downloads **images** and **files** in notion's page

- Exports **Nested Pages** in the page!

- Create **Front Matters** for supporting CMS (Title, Created Date, Tags)

> Add "Created" and "Tags" properties in your page. Then exporter will put them in the md file's front matter.

## Updates v1.1.0

- Change the output folder name `Notion_Exporter_Output/` to `notion_output/`

- Save token_v2 in `notion_output/notion_token.json` and read it when you use the exporter again.

- Fix the error that block.icon is not defined if the block has no icon in the title.


## Requirements

- token_v2: check the way to get Token_v2 in Notion-py [Quickstart](https://github.com/jamalex/notion-py#quickstart)

- url: the link that you will export

## Installation
``` bash
pip install notion2md
```

## Usage in Terminal
In your Bash/Zsh terminal,
``` bash
$python3 -m notion2md
#Token_v2: <your token_v2 on notion.so>
#Notion Page Url: <your notion page to export>
```

This will make `<date-page-title>.md` file in `your directory/notion_output` folder.

## Usage in Python

``` python
from notion2md import *

export_cli()
# Token_v2: <your token_v2 on notion.so>
# Notion Page Url: <your notion page to export>
```

## Output Structure.
The structure of the output looks like this path.

```
notion_output
├── notion_token.json
└── <main-page-title>/
    ├── <main-page-title>.md
    ├── download/
    │   └── ...
    ├── image/
    │   └── img_1.png
    │   └── ...
    └── subpage/
        └── ...
```

- in `subpage/`, there will be `image/`, `download/`, and `subpage/` folders if there are sub components in `sub page`.

## Todo

- convert other block types to md. 


## Previous Versions


### [Change Log](./change_log.md)

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
