# Pyobidl
Python 3 library for downloading (googledrive,mega,mediafire,directurl)
# Description
Pyobidl is a fast library for downloading (googledrive,mega,mediafire,directurl) using requests,mega.py
# Features v1.1.0
- Suport Mega Files and Folders Urls
- Suport Mediafire File Urls
- Suport Google Drive Files Urls
- Suport Direct Files Urls
# Quickstart & Installation
Pyobidl requires an installation of Python 3.6 or greater, as well as pip. (Pip is typically bundled with Python 
To install from the source with pip:
```
python -m pip install git+https://github.com/ObisoftDev/pyobidl
```
#Using pyobidl in a Python script
```
from pyobidl.downloader import Downloader
from pyobidl.utils import sizeof_fmt

def progress(dl:Downloader,filename:str,index:int,total:int,speed:int,time:int,args:tuple=None):
    print(f'{filename} {sizeof_fmt(index)}/{sizeof_fmt(total)} ({sizeof_fmt(speed)})',end='\r')
    pass
    
async def async_progress(dl:Downloader,filename:str,index:int,total:int,speed:int,time:int,args:tuple=None):
    print(f'{filename} {sizeof_fmt(index)}/{sizeof_fmt(total)} ({sizeof_fmt(speed)})',end='\r')
    pass
    
dl = Downloader(destpath='')
ouptut = dl.download_url(url='https://mega.nz/#F!IlxWwQJY!ZkcrapwfMxOjhhGXn5jEqQ',progressfunc=progress)
#ouptut = await dl.async_download_url(url='https://mega.nz/#F!IlxWwQJY!ZkcrapwfMxOjhhGXn5jEqQ',progressfunc=async_progress)
```
