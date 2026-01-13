---
slides:
  title: Doc as Code
---

# Doc as Code

Documentações Impressionantes

Note:
- O que iremos automatizar hoje?
- Quando entrei no Estado em 2009:
    - Documentos enviados em papel.
    - Pastas na rede e arquivos sem compartilhamento.
    - Caixas de e-mail sobrecarregadas.
    - Dificuldade de achar informação neste universo.
- Evolução de ferramentas:
    - Arquivos em núvem.
    - SEI.
- Mas qual problema atual?
    - Arquivos desinteressantes e difíceis de construir.
    - Fechados por padrão.
    - Informação fragmentada.

<!--s-->

## Agenda
- [Docs as code](https://www.writethedocs.org/guide/docs-as-code/).
- Pré-requisitos:
    - GitHub.
    - Instalações.
    - 101 comandos.
    - Markdown.
    - Site estático.
- Publicação automática.
- O que mais?

<!--s-->

## Docs as code

[Filosofia](https://www.writethedocs.org/guide/docs-as-code/) preconiza escrita de documentação com as [mesmas ferramentas utilizadas no desenvolvimento de softwares](https://meadapt.com/blog/pare-tudo-que-esta-fazendo-e-vem-conhecer-o-github/).

Note:
- Softwar nada mais é do que um conjunto organizado de arquivos de texto.
- Documentação em geral não é feita pois é um processo chato e moroso.
- Se a informação só existe na cabeça de quem a gerou ela não existe.
- Devemos colaborar com nós mesmos, pois você de 2 meses atrás não responde e-mail.
- Foco no trabalho de fato de escrever e não na forma.
- Do que precisamos:
    - Utilização de modelos amigáveis.
    - Foco no conteúdo ou texto.
    - Controle de versão via git.
    - Abertura de tickets para novas ideias ou revisões (Issues).
    - Revisões em pares.
    - Automatizações para construção e publicação.

<!--v-->

## Docs as code
- Exemplos:
  - [Site MeAdapt](https://meadapt.com).
  - [Site Automatiza.MG](https://automatiza-mg.github.io/automatizacoes/).
  - Esta apresentação.

<!--s-->

## Pré-requisitos

<!--v-->

## GitHub
- Já tem uma conta registrada?

<!--v-->

## Instalações
- Editor VsCode.
- Git.
- Python.

<!--v-->

## 101 comandos
- Terminal: pwd, ls, cd, mkdir, touch, cat, rm.
- Git: init, status, log, add, commit, checkout, clone, pull, push.

Note:
- Utilizados em 99% das vezes.

<!--v-->

## Markdown
- Cabeçalho: #
- Negrito: `**texto em negrito**`
- Itálico: `*texto em italico*`
- Citação: >
- Lista ordenada: 1. Primeiro
- Lista não ordenada: - Item
- Código em linha: "``"
- Links: `[]()`
- Imagens: `![]()` - [https://unsplash.com/](https://media.istockphoto.com/id/1679733776/photo/closeup-image-of-judge-gavel-and-text-product-liability.webp?a=1&b=1&s=612x612&w=0&k=20&c=KXqN8IRwVW7k3Nexdwol2K9ZJPWakOjC8tkg3UR1g9E=)

Note:
- Sintaxe utilizada para maioria das nossas necessidades.

<!--v-->

## Markdown Extendido (Atenção)
- Tabelas: [Table Generator](https://www.tablesgenerator.com/markdown_tables)
- Lista de Tarefas: - [ ] Tarefa 1
- Bloco de Código: "```"
- Emoji: :snake:
- Tachado: `~~tachado~~`
- Realçado: ==realçado==
- [Mermaid](https://mermaid.js.org/intro/)

<!--v-->

## Site estático

[Mkdoc](https://www.mkdocs.org/)

[Material for Mkdocs](https://squidfunk.github.io/mkdocs-material/)

<!--s-->

## Mkdocs

```
$ mkdocs new . # Para iniciar um projeto
$ mkdocs build # Conversão md para html (comando serve melhor)
$ mkdocs serve # Iniciar um servidor
$ mkdocs gh-deploy # Fazer deploy
$ mkdocs --help # Para pedir ajuda
```

<!--v-->

## Mkdocs

```
$ mkdir meu-primeiro-site-estatico
$ cd meu-primeiro-site-estatico
$ touch .gitignore # https://www.toptal.com/developers/gitignore/
$ touch requirements.txt # mkdocs on pypi
$ python -m venv venv # python3 -m venv venv no Linux
$ source venv/Scripts/activate # source venv/bin/activate
$ pip install -r requirements.txt
$ git init
$ git branch -M main # Pode ser configurado
$ git add .
$ git commit -m "Commit Inicial"
$ mkdocs new . # docs/ e mkdocs.yml
$ mkdocs serve # Testa mudanças ao vivo
```

<!--s-->

## Customizações
- Instalação de Pacote `pymdown-extensions`:

```
$ pip install pymdown-extensions

# mkdocs.yml
markdown_extensions:
  - pymdownx.tasklist
  - pymdownx.emoji
  - pymdownx.mark      # Realçado
  - pymdownx.tilde     # Tachado
  - pymdownx.highlight # Códigos
```

<!--v-->

## Customatizações

```
# Mermaid - não precisa instalar nada via pip

# mkdocs.yml
markdown_extensions:
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
```

<!--v-->

## Customatizações
- Instalação e customização do pacote [mkdocs-material](https://squidfunk.github.io/mkdocs-material/creating-your-site/):

```
$ pip install mkdocs-material

# mkdocs.yml
site_name: My site
site_url: https://mydomain.org/mysite
theme:
  name: material
```

<!--v-->

## Customatizações
Utilização Superfences

```
hl_lines="" linenums="" title="Meu Arquivo.py"
```

<!--s-->

## Publicação automática

```
# Criar repositório GitHub
git remote add origin <repo-path>.git # camg utilizar https
git add .
git commit -m "Finaliza primeira versão"
git push origin main
mkdocs gh-deploy # Verifica página publicada.
```

<!--s-->

## O que mais?

- Consute a documentação [Material](https://squidfunk.github.io/mkdocs-material/getting-started/) para saber como incluir:
    - [Sistema de cometários](https://squidfunk.github.io/mkdocs-material/setup/adding-a-comment-system/?h=comment).
    - [Versionamento](https://squidfunk.github.io/mkdocs-material/setup/setting-up-versioning/?h=versio).
    - [Firulas em geral](https://squidfunk.github.io/mkdocs-material/reference/grids/?h=grid).
    - E muito mais!!!

<!--s-->

# Fim