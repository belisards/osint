# Arquivamento

## Recursos gerais
[Bellingcat caixa de ferramenta](https://docs.google.com/spreadsheets/d/18rtqh8EG2q1xBo2cLNyhIDuK9jrPGwYr9DI2UncoqJQ/edit#gid=1720404390)

[Witness Archive Guide](https://archiving.witness.org/archive-guide/)

[Awesome Web Archiving](https://github.com/iipc/awesome-web-archiving)

[Web Archiving software comparison](https://docs.google.com/spreadsheets/d/1FqxwaZnIhhQ7jDCC-W64NMRf5rDeh2Shx3u01MsBmTQ/edit#gid=0)

## Web
### [Archive.is](https://archive.is)
- [Extensão](https://addons.mozilla.org/en-GB/firefox/addon/wayback-machine_new/) 
- [Pacote em Python](https://github.com/akamhy/waybackpy)
- [Automação com YouTube](https://github.com/bibanon/tubeup)

[Web Archive](https://web.archive.org/)

## Extensões
Use NO MÍNIMO um navegador separado, ou seja, diferente daquele que você navega. 

O Chrome costuma ter boas extensões, é possível usar variantes como o [Brave](https://brave.com/) ou o [Chromium](https://www.chromium.org/chromium-projects/).

- [Conifer](https://conifer.rhizome.org/)

- [Video download helper](https://www.downloadhelper.net/)

## CLI
### wget
[https://www.gnu.org/software/wget/](https://www.gnu.org/software/wget/)
Explore os parâmetros. Exemplo:

`wget -i links.txt`

### youtube-dl
[https://github.com/ytdl-org/youtube-dl](https://github.com/ytdl-org/youtube-dl)

Não se engane com o nome, funciona também outras redes

### snscrape
[https://github.com/JustAnotherArchivist/snscrape](https://github.com/JustAnotherArchivist/snscrape)

### you-get
[https://you-get.org/](https://you-get.org/)


## Plataformas
### Auto Archiver
[https://github.com/bellingcat/auto-archiver](https://github.com/bellingcat/auto-archiver)

### Archivematica
[https://www.archivematica.org/en/](https://www.archivematica.org/en/)

### Perma.cc
[https://perma.cc](https://perma.cc)

### Sugarcube
[https://sugarcubetools.net/](https://sugarcubetools.net/)

### Google Sheets + Python

```
!pip install snscrape
!pip install you-get

from google.colab import auth
from google.auth import default
from google.colab import drive

import gspread
import pandas as pd
import snscrape.modules.twitter as sntwitter
import os

auth.authenticate_user()
creds, _ = default()
gc = gspread.authorize(creds)

worksheet = gc.open('NOME_DA_SUA_PLANILHA').sheet1
drive.mount('/content/drive/')

df = pd.DataFrame(worksheet.get_all_values()[1:],columns=worksheet.get_all_values()[0])

```
