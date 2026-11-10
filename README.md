# Portfólio — Geison Bonaud

Meu portfólio pessoal: quem eu sou, o que estou construindo e como falar comigo.
Sou estudante de Engenharia de Software na UVA, no Rio de Janeiro, e procuro estágio em desenvolvimento, automação, dados ou IA.

Tema escuro e minimalista, em página única, com seções de **Início**, **Projetos**, **Sobre** e **Contato**.

## Projetos em destaque

| Projeto | O que é | Stack |
| --- | --- | --- |
| **PPRT.IA** | Plataforma que conecta placas NFC às avaliações no Google, com painel de gestão (placas, clientes, vendas, financeiro e métricas). | Next.js, TypeScript, Supabase, PostgreSQL, Tailwind CSS, Vercel |
| **Home Finance** | App de finanças para duas pessoas dividirem a casa: contas, compras, custo da casa, acerto entre moradores, planejamento e relatórios. Um produto NAUD. | React Native, Expo, TypeScript, Supabase, PostgreSQL, Vercel |

Cada projeto abre num modal com descrição, o que eu fiz, stack e links.

## Rodando localmente

Não tem build nem dependências para instalar. Basta servir a pasta:

```bash
python3 -m http.server 8000
```

Depois abra <http://localhost:8000>. Abrir o `index.html` direto (`file://`) pode falhar, porque alguns navegadores bloqueiam os scripts nesse modo.

## Estrutura

```
.
├── index.html     # a página inteira: template, estilos e a lógica dos projetos
├── support.js     # runtime que renderiza o componente no navegador
├── vendor/        # React e React DOM (usados pelo runtime)
└── assets/        # imagens dos projetos
```

O `index.html` nasceu de um mockup exportado de uma ferramenta de design (Design Component). Os valores de cor, tipografia, espaçamento e raio ficam nos estilos inline do próprio arquivo. `support.js` e `vendor/` fazem parte do runtime, não do design.

## Adicionando um projeto

1. Coloque a imagem em `assets/`.
2. No `<script>` no final do `index.html`, adicione um objeto à lista `list` dentro de `renderVals()`:

```js
{
  real: true, slot: false,
  title: 'Título do card', client: 'Nome · contexto',
  name: 'Nome', aria: 'Ver detalhes do Nome',
  img: './assets/imagem.png', pos: '50% 50%', fit: 'cover', bg: '#1B1B1B',
  alt: 'Descrição da imagem', caption: 'Legenda no modal',
  tag: 'Nome · projeto pessoal', gallery: false,
  intro: 'Resumo do projeto.',
  items: [{ t: 'Destaque:', d: 'o que foi feito.' }],
  stack: 'Tecnologia · Tecnologia',
  site: 'https://...', repo: 'https://github.com/...' // repo vazio esconde o botão
}
```

- `fit: 'contain'` com `bg` na cor da imagem evita cortar prints largos, como o de uma landing page.
- `gallery: true` mostra os espaços de prints extras no modal (hoje só o PPRT.IA usa).
- Itens com `slot: true` aparecem como cards vazios de "[Nome do projeto]".

## Contato

- GitHub: [github.com/Bonaud13](https://github.com/Bonaud13)
- LinkedIn: [linkedin.com/in/geison-bonaud](https://linkedin.com/in/geison-bonaud)
