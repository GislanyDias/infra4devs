# Nome do Projeto
> Um nome provisório que resuma bem a ideia. Seja criativo, mas claro!

## 👨‍🎓 Integrantes
- Eduardo Nogueira Alves
- Gislany Dias Formiga
- Igor Kádson de Souza Oliveira
- João Pedro de Lima e Silva

## 💡 Ideia Principal
Desenvolver agentes de inteligência artificial que faça deployment de aplicações em nuvem a partir do fornecimento dos seus respectivos códigos

## 🎯 Objetivos
- Identificar e instalar dependências do projeto;
- Containerizar aplicações;
- Realizar deployment das aplicações containerizadas;
- Disponibilizar o endpoint de acesso (inicialmente, um endereço de IP).

## 👥 Público-Alvo
Desenvolvedores de software ou pessoas que não tem skill de DevOps/SRE para realizar deployment de aplicações em ambientes de nuvem.

## 🤖 Agentes Envolvidos
Exemplo:
- Agente A - Collect: coleta dados
- Agente B - Checker: Verifica dependências e escreve prompts para uma llm gerar os passos de deploy
- 
- Agente C - Applier: Checa se o código de deploy está funcionando 

## 🧱 Tecnologias Pretendidas
- Python
- Possivelmente, terraform e ansible

> Justifique, sempre que possível, **por que escolheu cada ferramenta**.
> Python: Linguagem pretendida em virtude da facilidade de lidar com libs de langchain.
> Terraform: Ferramenta de automação que possui ampla comunidade de desenvolvimento e fornece meios de deployment de máquinas virtuais em diferentes cloud-providers (aws, gcp, openstack, etc.)
> Ansible: Ferramenta de automação que possui ampla comunidade de desenvolvimento e fornece meios de deployment de aplicações (python, node, react, java, cpp, etc.);

## 📦 Entradas e Saídas Esperadas
**Entradas:**
- Quais dados o sistema recebe?
- Um prompt contendo:
    - O código a ser buildado;
    - Um chave de api para conexão com o cloud-provider;

**Saídas:**
- Quais ações ou informações ele gera?
- O agente deve ser capaz de implantar a solução do cliente em um ambiente virtualizado, e retornar para ele o endpoint de acesso a aplicação.

## 🔁 Interação entre os Agentes
Collect -> Recebe prompts do cliente e filtra a requisição. Por exemplo, na sentença "considerando o código em anexo, faça deployment da aplicacao pra mim na aws considerando a chave da api xpto"
`collect` irá enviar o código para Checker.
Checker -> Ao receber o código, `checker` irá verificar as dependências e separar em arquivos json para facilitar a instalação durante o processo de deploy; Além disso, checker inicará uma conversa com outra llm (chatgpt, llama, deepseek, etc.) para receber orientações de deployment. A cada interação, envia o código recebido para `Applier` e aguarda um feedback dele.
Applier -> Aplica as instruções recebidas de `checker` e retorna um feedback (positivo ou negativo) para ele. Se o feedback for positivo, `checker` dá continuidade com a conversa com a outra llm
para receber novas instruções. Se for negativo, `checker` informa o problema e busca soluçÕes para retornar para `applier`.

## 🗂️ Organização e Planejamento do Projeto
O progresso deste projeto será monitorado através do **GitHub Projects**.

> Acesse a aba "Projects" do repositório para acompanhar:
- Tarefas pendentes
- Tarefas em andamento
- Tarefas concluídas

Cada integrante deve ser responsável por pelo menos uma tarefa no quadro.
Use etiquetas (labels) e comentários para detalhar o andamento e as decisões.

## 📌 Status Inicial do Projeto
- [ ] Ideia discutida e validada com o professor
- [ ] Estrutura básica do repositório criada
- [ ] Quadro no GitHub Projects criado
- [ ] Primeiras tarefas definidas e atribuídas

## 📄 Documentação Futura
Este repositório poderá incluir:
- Diagramas de arquitetura
- Relatórios parciais de progresso
- Scripts de testes ou simulações
- Resultados e conclusões finais

## 👨‍🏫 Acompanhamento pelo Professor
Para que o professor possa acompanhar e orientar o andamento do projeto, **adicione o usuário `igorbarcosta` como colaborador do repositório.**

### Como fazer:
1. Vá até a aba **"Settings"** do seu repositório.
2. Clique em **"Collaborators"** no menu lateral.
3. Digite o nome de usuário: `igorbarcosta`
4. Clique em **"Add collaborator"** e confirme.
