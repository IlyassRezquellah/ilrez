# Blogmaker

This is an ultra-simple self-hosted blog publishing solution made by Vitalik Buterin

### Dependencies

* pandoc
* rsync

### Pasos a seguir
1-Guardamos el archivo .md en la carpeta "posts" que esta en la raiz
2-Generamos el archivo .html con el comando ("python3 publish.py posts/name_file.md") en la carpeta raiz
3-Con el comando ("pandoc --mathjax name_file.md -o name_file.html") generamos el html con las formulas ready para ser añadidas al html generado por el paso 2
4-Vamos a site/general y buacamos el html generado en el paso 2 y añadimos la información que hay en el html generado en el paso 3 a al archivo generado en el paso 2
5-Volvemos a la carpeta raiz y ejecutamos el siguiente comando("python3 publish.py --sync") para que estos cambios se actualizen en el servidor y se publiquen oficialmente en la website que vera todo el mundo
### How to use

See the [posts](./posts) directory for what a post should look like. Posts must be written in [markdown](https://daringfireball.net/projects/markdown/syntax), and filenames must end in ".md". Dates must be in (yyyy/mm/dd) format. All posts must be in the posts directory.

If you need a post to use MathJaX to format LaTeX equations, add the line

```
[pandoc]: <> (--mathjax)
```

to the config at the top of the post.

To compile a post to html, run `./publish.py posts/name_of_post.md` (or `./publish.py posts/*` to recompile everything). Use `./publish.py --sync` to upload the latest version of your site to your server (make sure to put your server details, as well as the site title and icon, in [config.md](./config.md)).

For the server, the simplest setup is to use any VPS, `apt install apache2`, make sure apache2 is running, and just set the directory to /var/www/html.

### Misc

Credit to https://hackmd.io for CSS styles.
