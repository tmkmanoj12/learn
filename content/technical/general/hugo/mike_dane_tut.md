---
title: Mike_dane_tut
date: 2018-11-26T08:45:31.000Z
weight: 1
pre: <b>- </b>
chapter: false
---
{{% attachments /%}}

**Installation**

```bash
sudo apt-get install hugo
```

Go to folder structure and do

```bash
hugo new site <project_name>
```

A Bunch of folders will be created

**Folder_Structure**

- **archetypes**

  - If we had a website and we want to assign a page a author or specify will language it is written. Hugo lets you to add those kind of data i.e meatadata(data about data), so this metadata sits in archetypes folder

- **content**

  - content of website goes here

- **data**

  - Acts as databse for website
  - like having JSON files nd pulling data from it

- layouts - You can define complex layouts in a hugo - like same header and footer in all pages in webiste , like writing a header.html and footer.html

- **static**

  - this is where you store static assets - like css , js , images

- **themes**

  - we can download prebuit themes

- **config.toml**

  - these are the settings of the website
  - You can define

    - title of webiste
    - what language it is written in
    - base URL

**About Themes**

- If you want to download themes from hugo website just copy the repo URL and clone it in themes directory and then modfiy the `.toml` file

**About Content**

- You can add markdown files in content using

  ```bash
  hugo new manoj.md
  ```

- you can add subdirectories also and add content files

- Each folder should have `_index.md` because it would the home page for list

**Starting Server**

```bash
hugo server -D
```

- This `D` Option is for telling the server to include the draft files too otherwise we cant see the working files coz when we create content files it will set `draft = true` by default

**Content Organization**

- when you go the server you will see all the content files listed and when you click the route changes
- Hugo defines two seperate types of content(breakdowns all the content of the website into two types)

  - single pages

    - to serve only particular content

  - list pages

    - eg : Home page , to list other pages

- When you are doing just breakdown content into list pages and single pages

**Front Matter in Hugo**

- It is the metadata (data about our content files)
- Generally we store them in key value pairs
- can be written in

  - YAML
  - TOML
  - JSON - `Default`

**ArcheTypes**

- when we create a new content file we will get some front matter , how will it be created ?(using `archetypes`)

- in archetypes there is `default.md` folder

- That will be taken as reference for front matter - for all new files

- we can have different archetypes for different for different files

- Just you have to give the containing dir name in `archetype` folder

- If it cant find the container folder it will take from default files

**Short Code**

- If you want to add a video to your content instead of adding a lengthy `html` we can have snippets called `short codes`
- we can define our own short codes
- for eg : to embedd a youtube video `"{{ <youtube qtIqKaDlqXo>}}"`

- {{% notice info %}} "Please remove space between bracker and youtube"
{{% /notice %}}

**Taxonomies**

- How we logically group our content together
- 2 types

  - tags

    - Suppose if we want to tag different blogs with different key words
    - when you click on tags hufo automatically creates a page with tag in the route
    - when you create a new taxonomies you have to decalre the default `tags and categores` along with cusotm
    - Eg :

      ```toml
      [taxonomies]
      tag = "tags"
      category = "categories"
      mood = "moods"
      ```

      singular = plural syntax

  - categories

    - Group different pieces of content with different categories

- when you change `config.toml` you have to restart the `hugo` server

**Templates**

- piece of `html` which is same on every page for eg : menu bar html is a template
- allow you to overall html skeleton and you can inject specific content
- we can have a template for list pages and single pages

# listTemplates

- means template for list file use
- we can create in `layouts` folder with `_default` folder and `list.html` which is a page used to render

  #### Hugo variable

  - `{{.Content}}` which wll display the index content

    #### Hugo Function

  - In order to loop

    ```
    {{range .Pages}}
      {{.Title}}
      {{end}}
    ```

  - means i want to range over pages and display title

    ```
    {{range .Pages}}
      {{.URL}}
      {{end}}
    ```

  -means range over pages and display the route

## SingleTemplates

- means They are single page content
- we can create in `layouts` folder with `_default` folder and `single.html` which is a page used to render
- we can access default front matter variables `{{.Title}}` or `{{.Date}}`

## Home Page Template

- we can create in `layouts` folder with `index.html` file

  ### Section Templates

- we can create in `layouts` folder with `content` sub folders
## gist 

{{<gist tmkmanoj12 33454861b6f237ec00aa18942825acc9 "keymap.cson" >}}


{{<youtube qtIqKaDlqXo >}}


