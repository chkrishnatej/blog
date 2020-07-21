---
title: "Python 101 - Part 1"
date: "2019-01-11"
description: "Sample article for Series Part 1"
tags: [markdown, css, html, themes]
categories: [themes, syntax]
series: ["Python 101"]
draft: false
---
This article offers a sample of basic Markdown syntax that can be used in Hugo content files, also it shows whether basic HTML elements are decorated with CSS in a Hugo theme.
<!--more-->

## Headings

The following HTML `<h1>`—`<h6>` elements represent six levels of section headings. `<h1>` is the highest section level while `<h6>` is the lowest.

# H1
## H2
### H3
#### H4
##### H5
###### H6

{{< highlight python>}}
if name is "krishna":
    print("Grant access")
{{< /highlight >}}

<br><br>

```python {linenos=table,hl_lines=["8-13","15-17"],linenostart=199}
from django.shortcuts import render
import re

import requests, json, locale
from bs4 import BeautifulSoup


def index(request):
  cities = [
    {'state': 'rn', 'name': 'natal'}, 
    {'state': 'rn', 'name': 'mossoro'}
  ]

  fields = [
    'População',
    'IDHM'
  ]

  city_values = []


  def cityData(cities):
    city_data = []
    
    for item in cities:
      # convert and read in json
      item = json.dumps(item)
      item = json.loads(item)
      
      name = item['name']
      state = item['state']

      url_request = requests.get("https://www.ibge.gov.br/cidades-e-estados/"+ state +"/"+ name +".html")
      div_select = BeautifulSoup(url_request.content, 'html.parser')

      ul = div_select.find(class_='resultados-padrao')  
      city_label = ul.findAll("p", {"class": "ind-label"})
      city_value = ul.findAll("p", {"class": "ind-value"})
      
      data = []
      for label, value in zip(city_label, city_value):
        text_label = label.text
        text_value = value.text
        if text_label.split()[0] == fields[0] or text_label.split()[0] == fields[1]:
          data.append([text_label, text_value])
          city_values.append(text_value.split()[0])

      data.append([name, state])
      city_data.append(data)
    return city_data


  data = cityData(cities)
  
  locale.setlocale(locale.LC_ALL, 'pt_BR.UTF-8')
  sumPopulations = float(city_values[0]) + float(city_values[2])
  averageIDHM = (locale.atof(city_values[1]) + locale.atof(city_values[3])) / 2

  context = {
    "data": data,
    "sumPopulations": sumPopulations,
    "averageIDHM": averageIDHM
  } 

  return render(request, 'ibge/index.html', context)
```


<br><br>





{{< highlight html "lineos=true,linenostart=199">}}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
{{< /highlight >}}