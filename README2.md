<!doctype html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <title>Document</title>

</head>

<body>

<pre>

GET chinese_news/_search

{

  "query": {

    "bool": {

      "must": [

        {"match_phrase": {

          "content": "两个一百年"

        }

        },

        {

          "match_phrase":{

            "headline": "新华社长篇通讯"

          }

          }

      ],

      "filter": {

        "range": {

       "date": {

        "gte": "2017-01-18",

        "lte": "2018-05-18",

        "format": "yyyy-MM-dd"

      }

    }

      }

    }

  },

  "highlight" : {

        "fields" : {

            "content" : {}

        }

    }

}

</pre>

</body>

</html>
