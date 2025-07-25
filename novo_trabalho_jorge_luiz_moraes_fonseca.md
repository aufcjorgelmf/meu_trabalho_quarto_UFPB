::::::::::::::::::::::::::::::::::::::::: {#quarto-document-content .content .quarto-banner-title-block .page-columns .page-full role="main"}
:::::::::::::::::::: {#apresentação .section .level1 .page-columns .page-full}

# Revisão de Conceitos de Git, GitHub e Conceitos Básicos de Python


## 1 - Objetivo do Presente Trabalho ##

::: {.justify}
O presente trabalho tem como objetivos apresentar os fundamentos e comandos essenciais do sistema de controle de versão em ambiente local (*Git*), assim como em repositórios remotos (*GitHub*), este destinados à atuação colaborativa, abordando tópicos e comandos essenciais ao imediato emprego das mencionadas ferramentas. 
:::

::: {.justify}
O presente trabalho tem como objetivos apresentar os fundamentos e comandos essenciais do sistema de controle de versão **Git** e da plataforma de hospedagem e colaboração **GitHub**, de forma clara e objetiva acerca do funcionamento de ambientes locais e sua integração com repositórios remotos via GitHub, abordando tópicos e comandos essenciais ao imediato emprego dessas ferramentas.
:::

::: {.justify}
De igual modo, também é propósito do presente trabalho abordar tópicos iniciais acerca da linguagem Python, por meio de breve introdução à linguagem de programação **Python**, com foco em suas **estruturas básicas**, breve introdução à instalação de ambiente de desenvolvimento e uso de **pacotes e bibliotecas** voltadas a aplicações em contextos profissionais, educacionais e científicos.
:::

:::


## 2 - O Git – Sistema de Controle de Versão

::: {.justify}
O *Git* é uma ferramenta de linha de comando que permite o controle de versões de arquivos localmente e em equipe. Apresenta as seguintes características (não exaustivas):
:::
 - é *distribuído*, ou seja, cada desenvolvedor possui uma cópia completa do repositório (completo com histórico de versões);
 - apresenta *desempenho elevado*: operações como `commit`, `diff` e `merge` são rápidas e realizadas localmente;
 - permite o *rastreamento de histórico*: registra todas as alterações feitas no projeto com hash exclusivo (SHA-1);
 - apresenta *branching* leve e rápido*: criação e mudança entre ramos de desenvolvimento são eficientes;
 - *staging area*: área intermediária que permite selecionar quais alterações serão commitadas;
 - permite *desfazer alterações*: comandos como `reset`, `revert` e `checkout` ajudam a corrigir ou descartar mudanças;
 - *segurança*: histórico de versões é criptograficamente seguro e resistente a alterações maliciosas;
 - *funciona offline*: todas as operações principais funcionam sem conexão com a internet; e
 - *Integração com ferramentas*: pode ser usado com IDEs, editores de texto, CI/CD, entre outros.

### 2.1 - Comandos Git: Função, Exemplo e Contexto

| Comando       | O que faz                                                                 | Exemplo de uso                                | Pertence a       |
|---------------|---------------------------------------------------------------------------|------------------------------------------------|------------------|
| `git init`    | Inicializa um novo repositório Git local (cria a pasta `.git`).           | `git init`                                     | **Git (local)**  |
| `git add`     | Adiciona arquivos ou alterações à staging area (preparação para commit).  | `git add arquivo.txt`                          | **Git (local)**  |
| `git commit`  | Salva (confirma) as alterações preparadas com uma mensagem descritiva.    | `git commit -m "Adiciona relatório inicial"`   | **Git (local)**  |
| `git push`    | Envia os commits locais para um repositório remoto no GitHub.             | `git push origin main`                         | **GitHub**       |
| `git pull`    | Atualiza o repositório local com as alterações do repositório remoto.     | `git pull origin main`                         | **GitHub**       |
| `git clone`   | Copia um repositório remoto existente (por exemplo, do GitHub) para local.| `git clone https://github.com/usuario/proj.git`| **GitHub**       |

---

## 2.2 - O GitHub – Plataforma de Hospedagem e Colaboração
::: {.justify}
O *GitHub* é um serviço web que oferece interface gráfica, controle de acesso e funcionalidades colaborativas sobre repositórios Git. Apresenta as seguintes características (não exaustivas):

 - *Hospedagem de repositórios remotos*: centraliza projetos e os torna acessíveis pela web (públicos ou privados);
 - *Interface amigável*: permite visualização de código, commits, branches, PRs e histórico via navegador;
 - *Pull Requests (PRs)*: permitem propostas de alteração com revisão e comentários antes da fusão ao código principal;
 - *Issues*: sistema para rastreamento de erros, sugestões e tarefas;
 - *GitHub Actions*: integração contínua (CI/CD), automação de testes, deploy e tarefas administrativas;
 - *Wiki e Documentação*: cada repositório pode ter wiki própria e páginas com documentação (`README.md`, GitHub Pages);
 - *Controle de acesso e permissões*: configurações finas de acesso por usuário, equipe e organização;
 - *Integração com Git local*: comandos como `git push`, `git pull` e `git clone` permitem sincronização com o repositório remoto;
 - *Forks e colaborações externas*: permite duplicar projetos para contribuir sem afetar o original; e
 - *Insights e estatísticas*: gráficos de atividade, contribuições, commits e produtividade da equipe.


### 2.2.1 - Principais Ações no GitHub (via Interface Web)

| Ação                    | Descrição                                                                                  |
| ----------------------- | ------------------------------------------------------------------------------------------ |
| Criar repositório       | Gera um novo repositório remoto (público ou privado).                                      |
| Fork                    | Copia um repositório de outro usuário para seu perfil, permitindo contribuições indiretas. |
| Pull Request (PR)       | Solicita a fusão de alterações feitas em uma branch para a branch principal (ex: `main`).  |
| Merge Pull Request      | Aceita uma PR e incorpora as alterações no branch de destino.                              |
| Criar Issue             | Abre um item de tarefa, sugestão ou relato de problema.                                    |
| Criar Wiki              | Adiciona um espaço de documentação ao repositório.                                         |
| Criar Release           | Marca versões estáveis do projeto (com tags e changelog).                                  |
| Configurar Actions      | Automatiza CI/CD (testes, deploy, validações etc.).                                        |
| Gerenciar colaboradores | Define quem pode ler, escrever ou administrar o repositório.                               |
---

### 2.2.2 - Principais Comandos da GitHub CLI (gh)
  - A GitHub CLI (gh) é uma ferramenta oficial para interagir com o GitHub pela linha de comando.

| Comando                             | O que faz                                                    |
| ----------------------------------- | ------------------------------------------------------------ |
| `gh auth login`                     | Autentica o usuário na GitHub CLI (via token ou navegador).  |
| `gh repo create`                    | Cria novo repositório GitHub (sem abrir o navegador).        |
| `gh repo clone <user>/<repo>`       | Clona repositório diretamente com autenticação GitHub.       |
| `gh issue list` / `gh issue create` | Lista ou cria issues em um repositório.                      |
| `gh pr create`                      | Cria Pull Request a partir de uma branch.                    |
| `gh pr checkout <number>`           | Faz checkout local de uma PR específica.                     |
| `gh pr merge`                       | Aceita e realiza o merge de uma Pull Request.                |
| `gh release create <tag>`           | Cria uma nova release com tag associada.                     |
| `gh repo fork`                      | Cria fork de repositório no GitHub diretamente via terminal. |
| `gh gist create`                    | Cria um *gist* (snippet de código) no seu perfil GitHub.     |
---


### 2.2.3 - Exemplos práticos com o GitHub (gh)
#### - Criar um novo repositório no GitHub
`gh repo create nome-repositorio/documentacao-git --public --confirm`

#### - Clonar um repositório
`gh repo clone nome-repositorio/documentacao-git`

#### - Criar uma issue
`gh issue create --title "Corrigir README" --body "O arquivo README precisa ser atualizado com instruções de uso."`

#### - Criar uma pull request
`gh pr create --title "Adiciona função de análise" --body "Inclui análise de risco automatizada." --base main`

---


## 3 - Gerenciador de Pacotes Python: `pip`

O `pip` é o gerenciador oficial de pacotes do Python. Ele permite instalar, atualizar e remover bibliotecas de forma prática, a partir do repositório **PyPI (Python Package Index)**.

### 3.1 - Tabela de Comandos `pip` – Instalação e Gerenciamento de Pacotes Python

| Finalidade                         | Comando                                                | Exemplo                                                                  |
|-----------------------------------|---------------------------------------------------------|--------------------------------------------------------------------------|
| Instalar pacote                   | `pip install nome-do-pacote`                           | `pip install pandas`                                                     |
| Instalar versão específica        | `pip install nome==versão`                             | `pip install numpy==1.23.5`                                              |
| Instalar múltiplos pacotes via arquivo | `pip install -r requirements.txt`                 | `pip install -r requisitos.txt`                                          |
| Instalar a partir de repositório Git | `pip install git+URL`                              | `pip install git+https://github.com/usuario/projeto.git`                |
| Atualizar pacote                  | `pip install --upgrade nome-do-pacote`                 | `pip install --upgrade scikit-learn`                                     |
| Desinstalar pacote                | `pip uninstall nome-do-pacote`                         | `pip uninstall matplotlib`                                               |
| Listar pacotes instalados         | `pip list`                                              | `pip list`                                                               |
| Mostrar informações de pacote     | `pip show nome-do-pacote`                              | `pip show flask`                                                         |
| Gerar lista de pacotes instalados | `pip freeze > requirements.txt`                        | `pip freeze > requirements.txt`                                          |
| Atualizar o próprio `pip`         | `python -m pip install --upgrade pip`                  | `python -m pip install --upgrade pip`                                    |
| Criar ambiente virtual            | `python -m venv nome_ambiente`                         | `python -m venv venv`                                                    |
| Ativar ambiente virtual (Windows) | `venv\Scripts\activate`                                | `venv\Scripts\activate`                                                  |
| Ativar ambiente virtual (Linux/Mac) | `source venv/bin/activate`                           | `source venv/bin/activate`                                               |
---


git add .






