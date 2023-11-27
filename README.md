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
- [✒ Author](#-author)

<!-- ## 🎥 Implementation Video

In the GitHub edit, drag the video that it already puts on github itself. -->

<!-- ## 🎨 Layout

Layout developed by [Name](https://www.instagram.com/urlName/)

[![Layout in Figma](https://github.com/VagnerNerves/default-readme/blob/main/assets/layout-in-figma.svg)](https://www.figma.com/files) -->

## 👏 Learning and more Implementations

- [Modulo 1](https://nextjs.org/learn/dashboard-app/getting-started) - Instação

  Aprendido a instalar o projeto base.

  Para instalar um novo projeto execute o comando: [(documentação)](https://nextjs.org/docs/getting-started/installation)

  ```bash
  npx create-next-app@latest
  ```

- [Modulo 2](https://nextjs.org/learn/dashboard-app/css-styling) - CSS Styling

  Aprendio que podemos utilizar o [Tailwindcss](https://tailwindcss.com/) como padrão do projeto, ou criar um arquivo [nome do componente].module.css e importar na pagina utilizada. [Documentação Styling](https://nextjs.org/docs/pages/building-your-application/styling)

- [Modulo 3](https://nextjs.org/learn/dashboard-app/optimizing-fonts-images) - Otimização fonts and Images

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

- [Module 4](https://nextjs.org/learn/dashboard-app/creating-layouts-and-pages) - Layouts and Pages

  Na pasta app sao consideradas as rotas, mas cada pasta para ser considerado rota precisa ter um arquivo "page.tsx" se tiver outro nome de arquivo ele considera como componente e nao como rota.

  Tambem temos os arquivos "layouts.tsx" que servem para criar um layout padrao apartir da rota.

  [Segue a documentação dos routes](https://nextjs.org/docs/app/building-your-application/routing/defining-routes)

- [Module 5](https://nextjs.org/learn/dashboard-app/navigating-between-pages) - Navigate

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

- [Modulo 6](https://nextjs.org/learn/dashboard-app/setting-up-your-database) - Configuração do banco de dados e projeto

- [Modulo 7](https://nextjs.org/learn/dashboard-app/fetching-data) - Fetching Data

  Foi feito buscaa api para mostrar na pagina "app/dashboar/page.tsx" e falado sobre cascatas de solicitações e busca paralela de dados, Segue exemplo abaixo de busca paralela:

  ```bash
  export async function fetchCardData() {
    try {
      const invoiceCountPromise = sql`SELECT COUNT(*) FROM invoices`;
      const customerCountPromise = sql`SELECT COUNT(*) FROM customers`;
      const invoiceStatusPromise = sql`SELECT
          SUM(CASE WHEN status = 'paid' THEN amount ELSE 0 END) AS "paid",
          SUM(CASE WHEN status = 'pending' THEN amount ELSE 0 END) AS "pending"
          FROM invoices`;

      const data = await Promise.all([
        invoiceCountPromise,
        customerCountPromise,
        invoiceStatusPromise,
      ]);
      // ...
    }
  }
  ```

- [Modulo 8](https://nextjs.org/learn/dashboard-app/static-and-dynamic-rendering) - Renderização Estatica e Dinamica

  Para cancelar a renderização estatica pode-se usar o "next/cache" buscando o "unable_noStore" e usando nas funções. Segue exemplo:

  ```bash
  import { unstable_noStore as noStore } from 'next/cache';

  export async function fetchRevenue() {
    // Add noStore() here to prevent the response from being cached.
    // This is equivalent to in fetch(..., {cache: 'no-store'}).
    noStore();

    // ...
  }
  ```

- [Modulo 9](https://nextjs.org/learn/dashboard-app/streaming) - Transmissão

  O arquivo "logadin.tsx" é uma rquivo especial Nextjs, que colcoa o Loading até a pagina ser carregada.

  Para nao carregar o Loading para todas as rotas, podemos usar o [Grupo de Rotas](https://nextjs.org/docs/app/building-your-application/routing/route-groups) onde criar uma pasta "(NomeDaPasta)" e dentro dela signica que so vai ser executado no principal e nao nas outras rotas dentro.

  No react existe o "Suspense", ele ajuda a so exibir o componente depois que ele tiver carregado podendo assim mostrar um esqueleto ou um loading antes. segue o exemplo:

  ```bash
  import { Suspense } from 'react';
  import { RevenueChartSkeleton } from '@/app/ui/skeletons';

  <Suspense fallback={<RevenueChartSkeleton />}>
    <RevenueChart />
  </Suspense>

  ```

- [Modulo 10](https://nextjs.org/learn/dashboard-app/partial-prerendering) - Renderização parcial

  Foi falado sobre renderizaçãoes parciais e mostrado um pouco mais sobre o Suspense do react.

- [Modulo 11](https://nextjs.org/learn/dashboard-app/adding-search-and-pagination) - Pesquisa e paginação

  Utilizamos o "useSearchParams", "usePathname" e "useRouter" do "next/navigation" para busca via url no servidor, segue exemplo abaixo:

  ```bash
  const searchParams = useSearchParams();
  const pathname = usePathname();
  const { replace } = useRouter();

  function handleSearch(term: string) {
   const params = new URLSearchParams(searchParams);
   if (term) {
     params.set('query', term);
   } else {
     params.delete('query');
   }
   replace(`${pathname}?${params.toString()}`);
  }
  ```

  Foi utilizando tambem a bilioteca [use-debounce](https://www.npmjs.com/package/use-debounce) para só fazer a consulta se o usuairio parou realmente de digitar.

- [Modulo 12](https://nextjs.org/learn/dashboard-app/mutating-data) - Dados Mutantes

  Neste modulos aprendemos usar ações de servidor para inserir, editar e excluir. Olhe o arquivo "app/lib/actions.ts"

- [Modulo 13](https://nextjs.org/learn/dashboard-app/error-handling) - Tratamento de erros

  Para tratar um erro crie uma rquivo "erro.tsx" ele tem que ser "use client" e ter este padrão:

  ```bash
  'use client';

  import { useEffect } from 'react';

  export default function Error({
    error,
    reset,
  }: {
    error: Error & { digest?: string };
    reset: () => void;
  }) {
    useEffect(() => {
      // Optionally log the error to an error reporting service
      console.error(error);
    }, [error]);

    return (
      <main className="flex h-full flex-col items-center justify-center">
        <h2 className="text-center">Something went wrong!</h2>
        <button
          className="mt-4 rounded-md bg-blue-500 px-4 py-2 text-sm text-white transition-colors hover:bg-blue-400"
          onClick={
            // Attempt to recover by trying to re-render the invoices route
            () => reset()
          }
        >
          Try again
        </button>
      </main>
    );
  }
  ```

  Você tamnem pode criar aruivo para nao encontrado, criando um arquivo "not-found.tsx", veja como foi implementano na pasta "app/dashboard/invoicex/[id]/edit/".

- [Modulo 14](https://nextjs.org/learn/dashboard-app/improving-accessibility) - Melhorando a acessibilidade

  Foi falado sobre acessibilidade e verificado erros no servidor, para isso olhe o [commit](https://github.com/VagnerNerves/curse-learn-next.js/commit/98d598308dbd57dbfbbadc713b0d89e38dc9ddd7?diff=unified)

- [Modulo 15](https://nextjs.org/learn/dashboard-app/adding-authentication) - Adicionando autenticação

  Aprendemos sobre autenticação e autorização. Fizemso autenticação com o "NextAut", para ver as autterações olhe o [commit
  ](https://github.com/VagnerNerves/curse-learn-next.js/commit/950111d84ffdef2234a3266c0545828fa0e27cc4)

- [Modulo 16](https://nextjs.org/learn/dashboard-app/adding-metadata) - Adicionando Meta Data

  Para Adicionar Meta Data acesse o Layout ou page e coloque o comando:

  ```bash
  import { Metadata } from 'next';

  export const metadata: Metadata = {
    title: 'Acme Dashboard',
    description: 'The official Next.js Course Dashboard, built with App Router.',
    metadataBase: new URL('https://next-learn-dashboard.vercel.sh'),
  };
  ```

  Tambem temos o template que podemos usar na rota principal e nas rotas filhas so alterar o titulo segue exemplo abaixo:

  ```bash
  # Rota Pai
  import { Metadata } from 'next';

  export const metadata: Metadata = {
    title: {
      template: '%s | Acme Dashboard',
      default: 'Acme Dashboard',
    },
    description: 'The official Next.js Learn Dashboard built with App Router.',
    metadataBase: new URL('https://next-learn-dashboard.vercel.sh'),
  };
  ```

  ```bash
  # Rota Filho
  import { Metadata } from 'next';

  export const metadata: Metadata = {
    title: 'Invoices',
  };
  ```

## 💡 Technologies Used

- [x] [React](https://reactjs.org/)
- [x] [Nextjs](https://nextjs.org/)
- [x] [TypeScript](https://www.typescriptlang.org/)
- [x] [Tailwindcss](https://tailwindcss.com/)
- [x] [Use Debounce](https://www.npmjs.com/package/use-debounce)
- [x] [NextAult.js](https://next-auth.js.org/)

<!-- ## 📂 Folder Structure

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

This project is under the MIT license. See the [LICENSE](https://choosealicense.com/licenses/mit/) file for more details. -->

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
