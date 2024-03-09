# Astro Starter Kit: Minimal

```sh
npm create astro@latest -- --template minimal
```

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/withastro/astro/tree/latest/examples/minimal)
[![Open with CodeSandbox](https://assets.codesandbox.io/github/button-edit-lime.svg)](https://codesandbox.io/p/sandbox/github/withastro/astro/tree/latest/examples/minimal)
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/withastro/astro?devcontainer_path=.devcontainer/minimal/devcontainer.json)

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
├── src/
│   └── pages/
│       └── index.astro
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There's nothing special about `src/components/`, but that's where we like to put any Astro/React/Vue/Svelte/Preact components.

Any static assets, like images, can be placed in the `public/` directory.

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).

## Creamos componente Astro con destructuring objeto.

index.astro:

---
import Card from '../components/Card.astro';
import Cards from '../components/Cards.astro';
import Flexboxexample from '../components/Flexboxexample.astro';



---

<html lang="en">
	<head>
		<meta charset="utf-8" />
		<link rel="icon" type="image/svg+xml" href="/favicon.svg" />
		<meta name="viewport" content="width=device-width" />
		<meta name="generator" content={Astro.generator} />
		<title>Astro</title>
	</head>
	<body>
		<h1>Astro</h1>
		<!-- <Card title="Card1" text="card text 1"></Card>
		<Card title="Card2" text="card text 1"></Card>
		<Card title="Card3" text="card text 1"></Card> -->


			<Cards post={{
			name:"Mamie Barnett", imagen:"../../public/img-1.jpg", title:"Card1", text:"card text 1", date:"8/03/24"	
		}}/>
			<Cards post={{
			name:"Mamie Barnett2", imagen:"../../public/img-2.jpg", title:"Card1", text:"card text 1", date:"8/03/24"	
		}}/>
			<Cards post={{
			name:"Mamie Barnett3", imagen:"../../public/img-3.jpg", title:"Card1", text:"card text 1", date:"8/03/24"	
		}}/>

		<!-- <Flexboxexample/> -->
	</body>
</html>

/////////////////////////
/////////////////////////

Cards.astro:

---
// const {title, text, imagen,name,date} = Astro.props
const {post} = Astro.props
---

<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Astro CARD</title>
    <!-- <link rel="stylesheet" href="css/estilos-flex.css"> -->
    <!-- <link rel="stylesheet" href="css/estilos-grid.css" /> -->
  </head>
  <body>
    <div class="container__background-triangle">
      <div class="triangle triangle1"></div>
      <div class="triangle triangle2"></div>
      <div class="triangle triangle3"></div>
    </div>

    <div class="container__cards">
      <div class="card">
        <div class="cover__card">
          <img src={post.imagen} alt="" />
        </div>
        <h2>{post.title}</h2>
        <p>
          {post.text}
        </p>
        <hr />
        <div class="footer__card">
          <h3 class="user__name">{post.name}</h3>
          <i>{post.date}</i>
        </div>
      </div>

    </div>
  </body>
</html>


/////////////////////
/////////////////////

Hago destructuring:
{post:{title, text, imagen,name,date}}
Asi solo pongo  <img src={imagen} alt="" /> ,etc

Cards.astro:

---
// const {title, text, imagen,name,date} = Astro.props
const {post:{title, text, imagen,name,date}} = Astro.props
---

<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Astro CARD</title>
    <!-- <link rel="stylesheet" href="css/estilos-flex.css"> -->
    <!-- <link rel="stylesheet" href="css/estilos-grid.css" /> -->
  </head>
  <body>
    <div class="container__background-triangle">
      <div class="triangle triangle1"></div>
      <div class="triangle triangle2"></div>
      <div class="triangle triangle3"></div>
    </div>

    <div class="container__cards">
      <div class="card">
        <div class="cover__card">
          <img src={imagen} alt="" />
        </div>
        <h2>{title}</h2>
        <p>
          {text}
        </p>
        <hr />
        <div class="footer__card">
          <h3 class="user__name">{name}</h3>
          <i>{date}</i>
        </div>
      </div>

    </div>
  </body>
</html>


/////////////////////////////
/////////////////////////////
