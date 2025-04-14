# Infra4Devs! 

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
- Agente C - Applier: Checa se o código de deploy está funcionando 

## 🧱 Tecnologias Pretendidas

- Python
- Terraform
- Ansible

```
Escolhemos usar Python pela facilidade da equipe em usar a linguagem e pela ampla grade de frameworks que podem ajudar a resolver o nosso problema, como por exemplo, Langchain.
Terraform e Ansible são tecnologias de automação que são úteis para implantação e configuração de máquinas virtuais em diferentes cloud providers (AWS, GCP, OpenStack, etc).
```

## 📦 Entradas e Saídas Esperadas
**Entradas:**
- Um prompt contendo:
    - O código a ser buildado;
    - Um chave de api para conexão com o cloud-provider;

**Saídas:**
- O agente deve ser capaz de implantar a solução do cliente em um ambiente virtualizado, e retornar para ele as informações necessárias para acessar os componentes.

## 🔁 Interação entre os Agentes

<ul>
<li> Collect: </li>
<ul><li>Recebe prompts do cliente e filtra a requisição. Por exemplo, na sentença "considerando o código em anexo, faça deployment da aplicacao pra mim na aws considerando a chave da api xpto `collect` irá enviar o código para Checker.</li></ul>
<li>Checker:</li>
<ul><li>Ao receber o código, `checker` irá verificar as dependências e separar em arquivos json para facilitar a instalação durante o processo de deploy; Além disso, checker inicará uma conversa com outra llm (chatgpt, llama, deepseek, etc.) para receber orientações de deployment. A cada interação, envia o código recebido para `Applier` e aguarda um feedback dele.</li></ul>
<li>Applier:</li> 
<ul><li>Aplica as instruções recebidas de `checker` e retorna um feedback (positivo ou negativo) para ele. Se o feedback for positivo, `checker` dá continuidade com a conversa com a outra llm
para receber novas instruções. Se for negativo, `checker` informa o problema e busca soluçÕes para retornar para `applier`.</li></ul>

## 🗂️ Organização e Planejamento do Projeto

> Acesse a aba "Projects" do repositório para acompanhar:
- Tarefas pendentes
- Tarefas em andamento
- Tarefas concluídas


## 📌 Status Inicial do Projeto
- [x] Ideia discutida e validada com o professor
- [x] Estrutura básica do repositório criada
- [ ] Quadro no GitHub Projects criado
- [ ] Primeiras tarefas definidas e atribuídas

## 📄 Documentação Futura
Este repositório poderá incluir:
- Diagramas de arquitetura
- Relatórios parciais de progresso
- Scripts de testes ou simulações
- Resultados e conclusões finais
