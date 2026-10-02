# Central de Serviços de Rede

Aplicação Web estática (HTML + CSS) para registro e acompanhamento de
solicitações técnicas de uma central de serviços de rede. Desenvolvida como
avaliação individual (N1) da disciplina, a partir dos wireframes em `docs/`.

> **Observação:** o projeto não utiliza JavaScript, banco de dados nem servidor.

## Links

- **Repositório (GitHub):** https://github.com/RBastos93/dw1-n1-central-servicos-rede
- **Aplicação publicada (GitHub Pages):** https://rbastos93.github.io/dw1-n1-central-servicos-rede/

## Páginas

| Arquivo              | Descrição                                                        |
| -------------------- | ---------------------------------------------------------------- |
| `index.html`         | Página inicial: apresentação e cartões de serviços.              |
| `chamados.html`      | Indicadores, formulário de pesquisa/filtros e lista de chamados. |
| `abrir-chamado.html` | Formulário para abertura de um novo chamado.                     |

## Estrutura

```text
dw1-n1-central-servicos-rede/
├── index.html
├── chamados.html
├── abrir-chamado.html
├── README.md
├── docs/                     # wireframes de referência
└── assets/
    ├── css/
    │   ├── reset.css         # normalização entre navegadores
    │   ├── global.css        # variáveis, header, nav, footer, botões
    │   ├── index.css
    │   ├── chamados.css
    │   └── abrir-chamado.css
    └── img/                  # ilustrações SVG dos serviços
```

## Organização do CSS (separado por responsabilidade)

Cada página importa os arquivos nesta ordem:

1. `reset.css` — zera estilos padrão do navegador e aplica `box-sizing: border-box`.
2. `global.css` — tokens em variáveis CSS (`:root`) e componentes compartilhados
   (cabeçalho, navegação, rodapé, botões, títulos).
3. CSS da página — estilos específicos daquela tela.

## Requisitos técnicos atendidos

- **HTML semântico** — `header`, `nav`, `main`, `section`, `article`/`li`,
  `fieldset`/`legend`, `footer`.
- **CSS separado por responsabilidade** — reset, global e um arquivo por página.
- **Flexbox** — usado em todo o layout: cabeçalho, navegação, grade de cartões
  (`index`), indicadores, filtros, cartões de chamado e as grades de campos do
  formulário (sem uso de CSS Grid).
- **Box Model + `box-sizing: border-box`** — aplicado globalmente no `reset.css`.
- **Medidas relativas** — tipografia e espaçamentos em `rem`; larguras em `%`.
- **Contêiner fluido** — `.app` com `max-width` e centralização, adaptando-se à
  largura da tela.
- **Imagens adaptáveis** — `<img>` com `max-width: 100%` e `object-fit`, todas
  com texto alternativo (`alt`).
- **Media queries** — pontos de quebra em 992px, 768px e 560px.
- **Formulários HTML + validações nativas** — `required`, `minlength`,
  `maxlength`, `pattern`, `accept` e tipos adequados (`email`, `tel`,
  `datetime-local`, `file`). O formulário de abertura usa `method="post"` com
  `enctype="multipart/form-data"`, evitando expor os dados na URL.
- **Navegação consistente** — mesmo menu nas três páginas, com destaque visual
  da página atual (`.nav__item--ativo` + `aria-current="page"`).

## Responsividade

- **index**: a grade de cartões passa de 4 → 2 → 1 coluna.
- **chamados**: indicadores, filtros e cartões de chamado colapsam para uma
  coluna no celular.
- **abrir-chamado**: cada linha de campos vira uma coluna e os botões ocupam a
  largura disponível.

Não há rolagem horizontal em telas estreitas.

## Como visualizar localmente

Abra qualquer arquivo `.html` diretamente no navegador. Não há dependências nem
etapa de build.

## Publicação no GitHub Pages

1. Faça o push do projeto para um repositório público chamado
   `dw1-n1-central-servicos-rede`.
2. No GitHub, acesse **Settings → Pages**.
3. Em **Source**, selecione a branch `main` e a pasta `/root`.
4. Salve e aguarde a publicação; a URL gerada é a da aplicação.

## Dificuldades encontradas

- Utilizar a semântica do HTML5 (`header`, `nav`, `main`, `section`, `footer`,
  `fieldset`), já que estou mais acostumado a estruturar as páginas apenas com
  `div`. Foi preciso identificar o elemento semântico mais adequado para cada
  parte do layout em vez de recorrer a `div` por padrão.

## Partes não concluídas

Nenhuma. Todos os itens solicitados foram implementados.
