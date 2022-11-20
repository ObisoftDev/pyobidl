# Pyobidl
Python 3 library for downloading (googledrive,mega,mediafire,directurl)
# Description
Pyobidl is a fast library for downloading (googledrive,mega,mediafire,directurl) using requests,mega.py
# Features v1.1.0
- Asyncs methods
- Suport Mega Files and Folders Urls
- Suport Mediafire File Urls
- Suport Google Drive Files Urls
- Suport Direct Files Urls
# Quickstart & Installation
Pyobidl requires an installation of Python 3.6 or greater, as well as pip. (Pip is typically bundled with Python 
To install from the source with pip:
```
pip install https://github.com/ObisoftDev/pyobidl/archive/master.zip
```
- Using pyobidl in a Python script
```
from pyobidl.downloader import Downloader
from pyobidl.utils import sizeof_fmt

def progress(dl:Downloader,filename:str,index:int,total:int,speed:int,time:int,args:tuple=None):
    print(f'{filename} {sizeof_fmt(index)}/{sizeof_fmt(total)} ({sizeof_fmt(speed)})',end='\r')
    pass

dl = Downloader(destpath='')
ouptut = dl.download_url(url='https://mega.nz/#F!IlxWwQJY!ZkcrapwfMxOjhhGXn5jEqQ',progressfunc=progress)
```
- Using async pyobidl in a Python script
```
from pyobidl.downloader import AsyncDownloader
from pyobidl.utils import sizeof_fmt

async def progress(dl:AsyncDownloader,filename:str,index:int,total:int,speed:int,time:int,args:tuple=None):
    print(f'{filename} {sizeof_fmt(index)}/{sizeof_fmt(total)} ({sizeof_fmt(speed)})',end='\r')
    pass

dl = AsyncDownloader(destpath='')
ouptut = await dl.download_url(url='https://mega.nz/#F!IlxWwQJY!ZkcrapwfMxOjhhGXn5jEqQ',progressfunc=progress)
```
