<p align="center">
    <img src="https://drive.google.com/uc?export=view&id=15id50RkDQplGHQLVoLKVSX-J6H43iyIS" alt="logo" />
</p>

<h1 align="center">
    Anime-Tracker
</h1>

<p align="center">
 <img src="https://img.shields.io/github/stars/Bit-Tech-Team/Anime-Tracker?style=social" />
 <img src="https://img.shields.io/github/forks/Bit-Tech-Team/Anime-Tracker?style=social" />
 <img src="https://img.shields.io/github/v/release/Bit-Tech-Team/Anime-Tracker" />
 <img src="https://img.shields.io/github/downloads/Bit-Tech-Team/Anime-Tracker/total?color=blue" />
 <img src="https://img.shields.io/github/issues-closed-raw/Bit-Tech-Team/Anime-Tracker" />
 <img src="https://img.shields.io/github/issues-raw/Bit-Tech-Team/Anime-Tracker" />
 <img src="https://img.shields.io/github/issues-pr-closed-raw/Bit-Tech-Team/Anime-Tracker" />
</p>

## Introduction

<p>
Anime Tracker is a desktop application for windows, developed with electron + react, which allows you to search for animes through
a scene that can be passed through a url or by uploading an image from your PC.

This application was made possible thanks to the [soruly](https://github.com/soruly) api, don't forget to go through its repository and leave a star.

**This application was powered by trace.moe-api** <a href="https://github.com/soruly/trace.moe-api"><img width="20px" height="20px" src="https://www.seekpng.com/png/detail/101-1017465_github-github-icon-png-grey.png" /></a>
</p>

## Video Demo

<https://user-images.githubusercontent.com/31443880/178163036-2b315f26-2c07-458a-a5f3-8c25091c8a76.mp4>

## How to install

First go to the following link [here](https://github.com/Bit-Tech-Team/Anime-Tracker/releases/download/v1.0.4/AnimeTracker-Setup-1.0.4.exe) 
and the download will start automatically.

![image](https://user-images.githubusercontent.com/31443880/187171283-9d1e0bb1-67bd-448b-9d9d-b83a0ce8c356.png)

**NOTE: As you can see, windows tells you that it could be a malicious file, this is not true, it is because I have not added code signing yet, just click on save and that's it**

Now when you click on the installer you will get the following pop-up for the same reason mentioned above, we simply click on "more information" and we will get a button that says "run anyway", and the app will start installing

<table>
    <tr>
        <td>
            <img src="https://user-images.githubusercontent.com/31443880/187172346-8f5f0579-5463-4222-a1ee-e0118c541367.png" />
        </td>        
        <td>
            <img src="https://user-images.githubusercontent.com/31443880/187172607-04a4f859-99e9-48d8-bc9f-dd933ce82c1d.png" />
        </td>
    </tr>
</table>


## Last version available

🚀[v1.0.4](https://github.com/Bit-Tech-Team/Anime-Tracker/releases/download/v1.0.4/AnimeTracker-Setup-1.0.4.exe)

## Report a bug

🐛[create a new issue](https://github.com/Bit-Tech-Team/Anime-Tracker/issues/new)

## Deploy in local

First run **``yarn``** and this will install the necessary packages, then run **``yarn electron-dev``** to run the application in developer mode (**make sure that port 3000 is not in use**). If you want to compile the app run ``yarn electron-pack-build`` and this will create a folder called **dist** where the installation **.exe** is located.

**NOTE:** The command ``yarn electron-pack-build`` and ``yarn electron-pack-deploy`` only compile for windows, if you like to do it for **mac** change the following line in the **package.json**

Old:

    "electron-pack-build": "yarn build && electron-builder build --win -c.extraMetadata.main=build/electron.js --publish never",
    "electron-pack-deploy": "yarn build && electron-builder build --win -c.extraMetadata.main=build/electron.js --publish always",

New:

    "electron-pack-build": "yarn build && electron-builder build --mac --win -c.extraMetadata.main=build/electron.js --publish never",
    "electron-pack-deploy": "yarn build && electron-builder build --mac --win -c.extraMetadata.main=build/electron.js --publish always",

## Explanations

- If you want to show the **devTools** in developer mode, go to **public/electron.js** and change the following from **false** to **true**

        devTools: false, //change to false for production

- If you want to use the command ``yarn-electron-deploy`` to deploy into github (this create a new release draft that is necessary to the auto update) you need to change the following line in the **package.json**

    change this:

        "repository": {
            "type": "git",
            "url": "https://github.com/Bit-Tech-Team/Anime-Tracker.git"
        },

    to this with your configs:

        "repository": {
            "type": "git",
            "url": "https://github.com/your-username/your-repo.git"
        },

    **IMPORTANT:** in addition you must to create an environment variable in your OS named **GH_TOKEN** and put the val of your github token (you can create this in **github > settings > Developer settings**)

