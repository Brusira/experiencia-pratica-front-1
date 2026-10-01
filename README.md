# 🌱 Site Institucional da ONG

Site institucional multipágina para uma organização não governamental, desenvolvido com **HTML5 semântico** e **CSS3 puro** (sem frameworks, sem JavaScript). O projeto apresenta a missão da ONG, seus projetos sociais, oportunidades de voluntariado, formas de doação e um formulário de cadastro.

> 📚 **Projeto acadêmico.** Os textos, nomes e dados de contato são marcadores de posição (ex.: `[Nome da ONG]`) e devem ser substituídos pelas informações reais da organização.

---

## 📑 Sumário

- [Páginas](#-páginas)
- [Estrutura do repositório](#-estrutura-do-repositório)
- [Tecnologias](#-tecnologias)
- [Acessibilidade e boas práticas](#-acessibilidade-e-boas-práticas)
- [Design e identidade visual](#-design-e-identidade-visual)
- [Como executar](#-como-executar)
- [Personalização](#-personalização)
- [Limitações conhecidas](#-limitações-conhecidas)
- [Licença](#-licença)

---

## 📄 Páginas

| Página | Arquivo | Descrição |
|---|---|---|
| **Início** | `index.html` | Missão e propósito, valores (transparência, inclusão e impacto), chamadas para apoio e formulário de contato com dados de atendimento. |
| **Projetos** | `projetos.html` | Projetos sociais ativos com imagens, requisitos para voluntariado, modalidades de doação (Pix e recorrente) e depoimentos de voluntários e beneficiários. |
| **Cadastro** | `cadastro.html` | Formulário completo para voluntários e/ou doadores, dividido em blocos: tipo de cadastro, dados pessoais, contato e endereço. |

### Detalhes por página

**`index.html`**
- Cabeçalho com nome e lema da ONG
- Seções: *Nossa Missão e Propósito*, *Nossos Valores*, *Como Apoiar Nossa Causa* e *Fale Conosco*
- Formulário de contato (nome, e-mail, assunto e mensagem)

**`projetos.html`**
- *Projetos Sociais Ativos*: três projetos com imagem e legenda
- *Oportunidades de Voluntariado*: lista de requisitos e botão de ação
- *Campanhas e Formas de Doação*: doação via Pix e doação recorrente
- *Depoimentos e Impacto*: relatos em `<blockquote>` com `<cite>`

**`cadastro.html`**
- Campos com validação nativa do HTML5: CPF, telefone, CEP, e-mail, data de nascimento e seleção de estado (todas as 27 UFs)
- Máscaras de formato validadas por `pattern`:
  - CPF: `000.000.000-00`
  - Telefone: `(00) 00000-0000`
  - CEP: `00000-000`

---

## 🗂 Estrutura do repositório

```
.
├── index.html
├── projetos.html
├── cadastro.html
├── README.md
└── assets/
    ├── styles.css
    ├── institucional.webp
    ├── projeto-1.webp
    ├── projeto-2.webp
    └── projeto-3.webp
```

---

## 🛠 Tecnologias

- **HTML5** — marcação semântica (`header`, `nav`, `main`, `section`, `article`, `figure`, `blockquote`, `address`, `footer`)
- **CSS3** — variáveis customizadas (`:root`), Flexbox, media queries e pseudo-classes modernas (`:focus-visible`, `:user-invalid`)
- **Imagens WebP** — formato otimizado, servido com o elemento `<picture>`

Nenhuma dependência externa, build ou gerenciador de pacotes é necessário.

---

## ♿ Acessibilidade e boas práticas

- Link **"Pular para o conteúdo"** visível ao receber foco do teclado
- Navegação com `aria-label` e página atual indicada via `aria-current="page"`
- Todos os campos de formulário com `<label>` associado, `fieldset`/`legend` para agrupamento e atributos `autocomplete` adequados
- Textos de ajuda (`<small class="ajuda">`) e indicação de campos obrigatórios
- Imagens com texto alternativo (`alt`), dimensões declaradas (`width`/`height`) e `loading="lazy"`
- Estilo de foco visível (`:focus-visible`) para navegação por teclado
- Feedback de erro em campos apenas **após a interação** do usuário (`:user-invalid`)
- Respeito à preferência do sistema por movimento reduzido (`prefers-reduced-motion`)
- Meta tags `description` e `viewport` em todas as páginas, com `lang="pt-BR"`

---

## 🎨 Design e identidade visual

O layout é baseado em **cartões empilhados** sobre fundo claro, com uma folha de estilos única e centralizada (`assets/styles.css`).

| Token | Valor | Uso |
|---|---|---|
| `--cor-primaria` | `#2c6e49` | Links, botões, destaques |
| `--cor-primaria-escura` | `#1e4d33` | Títulos, hover |
| `--cor-fundo` | `#f4f6f5` | Fundo da página |
| `--cor-superficie` | `#ffffff` | Cartões |
| `--cor-erro` | `#b3261e` | Campos inválidos |

- **Fonte:** `Segoe UI`, com fallback para `Arial` e `sans-serif`
- **Largura:** 780 px nas páginas comuns e 640 px (classe `.estreito`) nas páginas de formulário
- **Responsividade:** abaixo de 480 px, os espaçamentos são reduzidos e os campos em linha dupla passam a ocupar uma coluna

---

## ▶️ Como executar

Não há etapa de instalação. Basta abrir o projeto no navegador.

**Opção 1 — Abrir diretamente**

```bash
git clone https://github.com/<seu-usuario>/<nome-do-repositorio>.git
cd <nome-do-repositorio>
```

Em seguida, abra o arquivo `index.html` no navegador.

**Opção 2 — Servidor local (recomendado)**

```bash
# Com Python
python -m http.server 8000

# Ou com Node.js
npx serve .
```

Acesse `http://localhost:8000`.

**Publicação no GitHub Pages**

1. Vá em **Settings → Pages**
2. Em *Source*, selecione a branch `main` e a pasta `/ (root)`
3. Salve e aguarde a URL ser gerada

---

## ✏️ Personalização

Antes de publicar, substitua os marcadores de posição:

- `[Nome da ONG]` — nome da organização (títulos, textos e rodapé)
- `[Telefone]` e `[E-mail]` — dados de contato (e os links `tel:` e `mailto:` correspondentes)
- Endereço e horário de atendimento na seção *Fale Conosco*
- Chave Pix (`00.000.000/0001-00`) em `projetos.html`
- Descrições dos projetos, depoimentos e nomes dos citados
- Imagens em `assets/`, mantendo os mesmos nomes de arquivo ou ajustando os caminhos nos HTMLs

Para alterar cores, tipografia e espaçamentos, edite as variáveis no bloco `:root` de `assets/styles.css`.

---

## ⚠️ Limitações conhecidas

- Os formulários (`index.html` e `cadastro.html`) usam `action="#"` e **não enviam dados** a nenhum servidor. Para uso real, é necessário integrar um back-end ou um serviço de formulários.
- Não há máscaras automáticas de digitação; o usuário deve digitar CPF, telefone e CEP já no formato indicado.
- Os botões de doação direcionam para a página de cadastro, sem integração com meio de pagamento.
- Os dados de CPF coletados exigem tratamento conforme a **LGPD** caso o site seja colocado em produção.

---

## 📜 Licença

Projeto acadêmico, sem fins comerciais.