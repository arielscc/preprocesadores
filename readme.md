# Pre Processors

## Pug

Is an HTML preprocessor, use:

Install:

```bash
npm i pug-cli -g
```

Use:

```bash
pug -w --pretty landing.pug
```

### Anidacion

```pug
doctype html
html(lang="es")
  head
    meta(charset="UTF-8")
    link(rel="stylesheet",href='css/ejercicio-pug.css')
  body
    header
      h1 Games Page
      a.boton Registros
    section.intro
      .intro__imagen: img(src="images/imagen.png", alt="", srcset="")
      .intro__contenido
```

### Variables

You can declare variables using:

Single Vars:

```pug
-var variable = 'content'

//- You can use this variable
h1 #{variable}

//- or

h1=variable
```

Multiple Vars:

```pug
-var titles=['title_1', 'text', 'paragraph']

h1 #{titles[0]}
p=titles[2]

```

### Loops

```pug
-var games = ['title_game_1', 'title_game_2', 'title_game_3', 'title_game_4']
ul
  each game in games
    li #{game}
```

### Conditionals

```pug
-var nombre = 'ariel'

if user
  a.boton Hi #{user}
else
  a.boton Login
```

### Mixins

```pug
mixin box(image, title, content)
  .box
    .box_image: img(src=image, alt=title, srcset="")
    .box_content
      h3 #{title}
      p #{content}

body
  //- ...
  +caja(image, game, 'some content')
```

### Includes

```pug
body
  include path/file.pug
```

### export

in `landing.pug`:

```pug
extends path/template.pug
block content

  h1 Hello world
```

in `template.pug`:

```pug
body
  include path/header.pug
  block content
  include path/footer.pug
```

`block content` includes content on `template.pug`

## LESS
