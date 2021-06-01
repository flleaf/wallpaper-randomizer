# wallpaper-randomizer

A Termux project for applying random image in the chosen folder as a phone wallpaper

## Installation

```bash
curl -O https://raw.githubusercontent.com/Illirick/wallpaper-randomizer/main/change-wallpaper && chmod u+x change-wallpaper && mv change-wallpaper $PREFIX/bin/
```

You can also install script that let you change wallpaper by pressing on notification notification:

```bash
curl -O https://raw.githubusercontent.com/Illirick/wallpaper-randomizer/main/wallpaper-notification && chmod u+x wallpaper-notification && mv wallpaper-notification $PREFIX/bin/
```

## Usage

It's pretty straightforward:

```bash
change-wallpaper [path to the folder]
```

For notification:

```
wallpaper-notification [path to the folder]
```

## Changing wallpaper every interval of time (I can't speak)

First we need to create a script for the specific folder

```bash
touch ~/change-wallpaper && chmod u+x change-wallpaper && echo "change-wallpaper [your folder]" > ~/change-wallpaper
```

Then we need to actually put it on scheduler

**note**: you need to not only install *termux-api* package but also install *termux:API* app from Play Market or F-Droid

```bash
termux-job-scheduler -s ~/change-wallpaper --period-ms [period in milliseconds] --persistent true
```

**note**: if you are using android 7 or later then the minimum period is 900 000 milliseconds (or 15 minutes)
