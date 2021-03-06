# Safari bookmarks jsonizer

将 Safari 导出的书签文件转换为 JSON 格式的文件

## 运行

1. 创建并激活虚拟环境，使用的是 Python 3.6.2 开发

    ```
    virtualenv --no-site-packages env
    source env/bin/activate
    ```

1. 安装

    ```sh
    pip install safari-bookmarks-jsonizer
    ```

1. 使用

    ```sh
    jsonize -i ./Safari\ Bookmarks.html -o ./result.json
    ```

## 目标文件格式

导出的 JSON 格式为

```JSON
{
    "title": "分类名称",
    "catelogs": [
        {
            "address": "书签地址",
            "name": "书签名字",
            "favicon": "书签网站的图标，选填，App 会通过网站规范进行获取",
            "remark": "对书签的备注，选填"
        },
        {
            "//": "..."
        }
    ],
    "categories": [
        {
            "title": "二级分类名称",
            "catelogs": [
                {
                    "//": "...",
                }
            ],
            "categories": []
        }
    ]
}
```

## 帮助

```sh
jsonize -h
```

```
transform.py -i <input file> -o <output file>
transform.py -input <input file> -o <output file>

other options:
--ignore-folder: an array of folder names which and bookmarks in which will not appear in the result json file
--ignore-items: an array of bookmark names which will not appear in the result json file
--only-extract-folders: an array of folder names, bookmarks in which will be appear in the result json file, but not include the ones in subfolder name of which
--only-extract-items: an array of bookmark names which will appear in the result json file
```


