<p align="center">
  <img width="200px" alt="Curse Learn Next.js" title="Curse Learn Next.js" src=".github/logonextjs.png" />
  
  <h1 align="center">Curse Learn Next.js</h1>

  <p align="center">
    🔗 <a href="https://curse-learn-next-js-vagnernerves.vercel.app/">https://curse-learn-next-js-vagnernerves.vercel.app/</a> 🔗
  </p>  
  
  Este projeto faz parte do [curso do Next.js](https://nextjs.org/learn/dashboard-app).
</p>

## 🧭 Table of contents

- [🧭 Table of contents](#-table-of-contents)
- [👏 Learning and more Implementations](#-learning-and-more-implementations)
- [💡 Technologies Used](#-technologies-used)
- [📂 Folder Structure](#-folder-structure)
- [🚀 Running the Project](#-running-the-project)
  - [Back-end](#back-end)
  - [Front-end Web](#front-end-web)
  - [Mobile](#mobile)
- [📝 Routes](#-routes)
- [🌎 License](#-license)
- [✒ Author](#-author)

<!-- ## 🎥 Implementation Video

In the GitHub edit, drag the video that it already puts on github itself. -->

<!-- ## 🎨 Layout

Layout developed by [Name](https://www.instagram.com/urlName/)

[![Layout in Figma](https://github.com/VagnerNerves/default-readme/blob/main/assets/layout-in-figma.svg)](https://www.figma.com/files) -->

## 👏 Learning and more Implementations

- Modulo 1 - Instação

  Aprendido a instalar o projeto base.

  Para instalar um novo projeto execute o comando: [(documentação)](https://nextjs.org/docs/getting-started/installation)

  ```bash
  npx create-next-app@latest
  ```

- Modulo 2 - CSS Styling

  Aprendio que podemos utilizar o [Tailwindcss](https://tailwindcss.com/) como padrão do projeto, ou criar um arquivo [nome do componente].module.css e importar na pagina utilizada. [Documentação Styling](https://nextjs.org/docs/pages/building-your-application/styling)

- Modulo 3 - Otimização fonts and Images

  O Next possui o module "next/font/google" onde podemos importar as conts do google assim:

  ```bash
  import { Inter, Lusitana } from 'next/font/google';

  export const inter = Inter({ subsets: ['latin'] });

  export const lusitana = Lusitana({
    weight: ['400', '700'],
    subsets: ['latin'],
  });
  ```

  Segue [documentação das Fonts](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) se usa Tailwind CSS olhe a parte dele de como usar.

  Sobre Imagens o Next possui o modulo "next/image" onde ele optimza as imagens, segue exemplo abaixo:

  ```bash
  import Image from 'next/image';

  <Image
    src="/hero-desktop.png"
    width={1000}
    height={760}
    className="hidden md:block"
    alt="Screenshots of the dashboard project showing desktop version"
  />
  <Image
    src="/hero-mobile.png"
    width={560}
    height={620}
    className="block md:hidden"
    alt="Screenshot of the dashboard project showing mobile version"
  />
  ```

  Segue a [documentação das Images](https://nextjs.org/docs/app/building-your-application/optimizing/images).

- Module 4 - Layouts and Pages

  Na pasta app sao consideradas as rotas, mas cada pasta para ser considerado rota precisa ter um arquivo "page.tsx" se tiver outro nome de arquivo ele considera como componente e nao como rota.

  Tambem temos os arquivos "layouts.tsx" que servem para criar um layout padrao apartir da rota.

  [Segue a documentação dos routes](https://nextjs.org/docs/app/building-your-application/routing/defining-routes)

- Module 5 - Navigate

  Para navegação de rotas o Next possui o modulo "next/link", segue exemplo:

  ```bash
  import Link from 'next/link';

  <Link
    key={link.name}
    href={link.href}
    className="flex h-[48px] grow items-center justify-center gap-2 rounded-md bg-gray-50 p-3 text-sm font-medium hover:bg-sky-100 hover:text-blue-600 md:flex-none md:justify-start md:p-2 md:px-3"
    >
      <LinkIcon className="w-6" />
      <p className="hidden md:block">{link.name}</p>
  </Link>
  ```

  [Segue documentação do Linking](https://nextjs.org/docs/app/building-your-application/routing/linking-and-navigating#how-routing-and-navigation-works)

  Para conseguir pegar a rota em que voce esta, podemos user o "usePathname" do module "next/navigatio", com ele retorna a rota que estamos. Segue exemplo abaixo:

  ```bash
  'use client';

  import { usePathname } from 'next/navigation';

  const pathname = usePathname();

  console.log(pathname)
  ```

## 💡 Technologies Used

- [x] [React](https://reactjs.org/)
- [x] [Nextjs](https://nextjs.org/)
- [x] [TypeScript](https://www.typescriptlang.org/)
- [x] [Tailwindcss](https://tailwindcss.com/)

## 📂 Folder Structure

```plainText
app
.
├── __tests__
├── android                     # Native android files
├── ios                         # Native ios files
├── src                         # Source files
│   ├── @types                  # Contains all global definitions of types and interfaces
│   ├── assets                  # Contains Js bundles assets. e.g: icons, splash, images etc...
│   ├── components              # Contains all global react components
│   ├── context                 # All contexts
│   ├── constants               # Constants files
│   ├── hooks                   # Cstomized hooks
│   ├── navigation
│   ├── screens
│   ├── services                # Contains external and api services
│   ├── App                     # Aplication entry
.
.
├── index                       # Bundle entry
.
.
└── README.md
```

## 🚀 Running the Project

### Back-end

Clone the project

```bash
  git clone https://link-para-o-projeto
```

Enter the project directory

```bash
  cd my-project
```

Install with dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```

### Front-end Web

Clone the project

```bash
  git clone https://link-para-o-projeto
```

Enter the project directory

```bash
  cd my-project
```

Install with dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```

### Mobile

Clone the project

```bash
  git clone https://link-para-o-projeto
```

Enter the project directory

```bash
  cd my-project
```

Install with dependencies

```bash
  npm install
```

Start the server

```bash
  npx expo start
```

- IOS:

```bash
  npx pod-install && npx react-native run-ios
```

- Android:

```bash
  npx react-native run-android
```

## 📝 Routes

[![Run in Postman](https://github.com/VagnerNerves/default-readme/blob/main/assets/run-in-postman.svg)](https://app.getpostman.com/run-collection/link)
[![Run in Insomnia](https://github.com/VagnerNerves/default-readme/blob/main/assets/run-in-insomnia.svg)](https://insomnia.rest/run/?label=NAMEPROJECT&uri=LINK)

## 🌎 License

This project is under the MIT license. See the [LICENSE](https://choosealicense.com/licenses/mit/) file for more details.

## ✒ Author

<p align="center">
  <img width="200px" alt="Author Vagner Nerves" title="Author Vagner Nerves" src="https://github.com/VagnerNerves/default-readme/blob/main/assets/VagnerNerves.svg" />

  <h3 align="center">Vagner Nerves</h3>
  
  <p align="center">  
    Made with love and hate 😅, get in touch!
  </p>
</p>  
  
<div align="center">

[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-1f6feb?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/vagnernervessantos/)](https://www.linkedin.com/in/vagnernervessantos/)
[![Gmail Badge](https://img.shields.io/badge/-vagnernervessantos@gmail.com-1f6feb?style=flat-square&logo=Gmail&logoColor=white&link=mailto:vagnernervessantos@gmail.com)](mailto:vagnernervessantos@gmail.com)
[![GitHub Badge](https://img.shields.io/badge/-GitHub-1f6feb?style=flat-square&logo=GitHub&logoColor=white&link=https://github.com/VagnerNerves)](https://github.com/VagnerNerves)

</div>
