# CineMusic

  O CineMusic é a sua base de dados definitiva, construída pela comunidade, para explorar a intertextualidade entre a música e o cinema.

  Nascido da paixão por trilhas sonoras e análise musical, o CineMusic vai além de listar músicas: ele se propõe a catalogar e validar as referências cruzadas, aquele momento em que uma trilha sonora de filme ou série se inspira ou faz uma citação direta a uma obra musical clássica, popular ou anterior.

## Como Funciona?

  Usuários especialistas podem cadastrar referências detalhadas, fornecendo a justificativa e tags técnicas (como motivo temático ou instrumentação).
  
  A credibilidade é construída por meio do voto. Críticos, pesquisadores e fãs podem votar ('Concordo' ou 'Discordo') e justificar a validade de uma referência, elevando o rigor da base de dados.
  
  Fãs e pesquisadores podem filtrar referências por Status de Validação ('Validada' ou 'Em Discussão') e, crucialmente, acessar links diretos (Spotify, YouTube, etc.) para comparar o trecho do filme com a inspiração original imediatamente.

O CineMusic transforma a experiência de assistir a um filme em uma jornada de descoberta musical e análise crítica. É o ponto de encontro entre o entusiasta cinematográfico e o musicólogo.



# Equipe: Ana Carolina e Ana Clara ❤️🎵

Descrição do problema: Críticos, estudantes e entusiastas de música de cinema frequentemente identificam referências e inspirações em trilhas sonoras (ex: um tema de filme que soa como uma obra clássica anterior). 

A dificuldade é: Atualmente, essa análise é dispersa em fóruns, artigos e conversas informais. Não há uma plataforma centralizada e colaborativa que permita catalogar, comparar e, crucialmente, validar essas referências de forma estruturada. Isso dificulta a pesquisa acadêmica e a discussão precisa sobre a intertextualidade musical no cinema.

Descrição da solução: O CineMusic será um sistema de base de dados colaborativa focado em referências musicais cruzadas entre obras de cinema/audiovisual e músicas de referência (clássicas, populares, etc.).

Funcionalidades principais: 

Cadastro de Entradas: O usuário especialista pode cadastrar uma Referência Cruzada, que liga um Trecho Musical do Filme (Obra A) a um Trecho Musical de Referência (Obra B/Compositor).

Validação Comunitária: Outros usuários podem votar/avaliar a referência (ex: "Concordo", "Discordo") e deixar comentários. A referência só é considerada Validada pelo sistema após um número X de aprovações.

Visualização: O sistema permite a consulta das referências e exibe o Status de Validação (Não Validada, Em Discussão, Validada).


# História do Usuário

Como usuário especialista, eu preciso cadastrar uma Referência Cruzada (conectando um Trecho Musical de Filme a um Trecho Musical de Referência) para que a comunidade possa analisar, debater e validar a conexão musical proposta.

Como um Especialista em Trilhas Sonoras, eu desejo adicionar tags detalhadas (como Instrumentação, Motivo Temático, Período Clássico, etc.) ao registrar uma Referência Cruzada, permitindo que outros usuários possam filtrar o conteúdo com maior precisão técnica e acadêmica.

Como um Crítico de Cinema e Música, eu quero votar e justificar minha concordância ou discordância em uma Referência Cruzada já existente, garantindo que a base de dados mantenha um alto nível de credibilidade e rigor na análise intertextual.

Como um fã de Cinema e Música, eu quero encontrar as referências e inspirações musicais da trilha sonora da obra que estou assistindo, para que eu possa aprofundar meu entendimento e apreciação sobre a intertextualidade musical no cinema.

Como usuário comum, eu gostaria de acessar todas as músicas de um filme/série com mais facilidade, eliminando a necessidade de realizar pesquisas extensas em múltiplas plataformas.

Como um fã de Cinema e Música, eu desejo clicar no link de uma Referência Válida, para ser levado diretamente ao trecho musical correspondente (no Spotify, YouTube ou outra plataforma), permitindo a comparação imediata do trecho do filme com a inspiração original.

Como pesquisador, eu preciso filtrar as referências por Status de Validação ("Validada" ou "Em Discussão"), de forma a focar minha pesquisa apenas nas conexões que já possuem maior aceitação e consenso da comunidade especializada.

# Casos de Uso

Cadastrar Referência Cruzada (Inclui a adição de Tags técnicas).
Votar e Justificar Avaliação (Para validar ou rejeitar uma referência).
Consultar Trilha Sonora Completa (Para acessar todas as músicas de um filme/série).
Buscar e Filtrar Referências (Permite pesquisar por obra, compositor ou Status de Validação).
Visualizar Links de Comparação (Para acessar diretamente os trechos musicais no Spotify/YouTube).
## 1. UC-01: Cadastrar Referência Cruzada

### 1.1. Visão Geral

* **ID do Caso de Uso:** UC-01
* **Nome:** Cadastrar Referência Cruzada
* **Atores:** Usuário Especialista
* **Descrição:** Inserir uma nova conexão musical no banco de dados, enriquecida com detalhes técnicos, para iniciar o processo de validação comunitária.

### 1.2. Condições

* **Pré-condições:** O usuário especialista deve estar logado no sistema.
* **Pós-condições:** Uma nova Referência Cruzada, com seus respectivos links e tags, é registrada no sistema, aguardando a votação da comunidade.

### 1.3. Fluxo Principal de Eventos

1.  O **Usuário Especialista** acessa a tela de cadastro.
2.  O sistema exibe o formulário.
3.  O usuário insere os dados da **Obra A** (Filme/Trecho/Link) e **Obra B** (Referência/Compositor/Link).
4.  O usuário adiciona uma **Justificativa** detalhada.
5.  O usuário adiciona **Tags técnicas** (ex: Instrumentação, Motivo Temático).
6.  O usuário confirma o cadastro.
7.  O sistema registra a nova referência com o status inicial **"Não Validada"**.

***

## 2. UC-02: Votar e Justificar Avaliação

### 2.1. Visão Geral

* **ID do Caso de Uso:** UC-02
* **Nome:** Votar e Justificar Avaliação
* **Atores:** Usuário Comum (incluindo Críticos)
* **Descrição:** Permitir que o usuário contribua para a credibilidade da referência, registrando seu voto ("Concordo"/"Discordo") e fornecendo uma justificativa (comentário).

### 2.2. Condições

* **Pré-condições:** O usuário deve estar logado e a Referência Cruzada já deve estar cadastrada e visível.
* **Pós-condições:** O voto do usuário e a justificativa são registrados, e o Status de Validação da Referência é potencialmente atualizado.

### 2.3. Fluxo Principal de Eventos

1.  O Usuário acessa a página de uma Referência Cruzada específica.
2.  O sistema exibe as opções de voto: **"Concordo"** ou **"Discordo"**.
3.  O usuário seleciona uma opção de voto.
4.  Opcionalmente, o usuário adiciona um **comentário detalhado (justificativa)**.
5.  O sistema registra o voto e o comentário associado.
6.  O sistema **recalcula o score** da referência. Se o score atingir limites predefinidos, o **Status de Validação é atualizado** (para "Em Discussão", "Validada" ou "Rejeitada").

### 2.4. Fluxo Alternativo

* **FA-01: Mudança de Voto:** Se o usuário já tiver votado, o sistema permite **alterar o voto** e, se for o caso, modificar a justificativa.

