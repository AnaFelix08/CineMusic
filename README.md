# CineMusic
Entregáveis do projeto CineMusic.

# 🎵 CineMusic - Dossiê de Análise e Modelagem

## 🚀 Semana 1: Requisitos e Histórias de Usuário

O projeto CineMusic visa criar uma plataforma de referência cruzada de trilhas sonoras.

### Histórias de Usuário (HUs)

* **HU01 - Busca de Obras:** Como usuário, eu quero poder **buscar por obras audiovisuais (filmes, séries, documentários)** de forma rápida para encontrar suas trilhas.
* **HU02 - Visualização da Trilha:** Como fã, eu quero poder **consultar a lista completa de músicas de uma obra**, com compositores e trechos.
* **HU03 - Busca de Referência Avançada:** Como pesquisador, eu quero poder **buscar referências cruzadas** (músicas que se referenciam) por tags ou motivos temáticos.
* **HU04 - Link de Comparação:** Como fã, eu quero poder **acessar um link externo** que compare os trechos musicais referenciados.
* **HU05 - Cadastro de Referência (Especialista):** Como especialista, eu quero **cadastrar uma nova referência cruzada** entre duas obras para enriquecer o banco de dados.
* **HU06 - Votação/Validação:** Como especialista ou fã, eu quero poder **votar (validar/invalidar) uma referência** e, **opcionalmente, deixar um comentário** para justificar meu voto.
* **HU07 - Tags Técnicas (Especialista):** Como especialista, eu quero poder **adicionar tags técnicas ou temáticas** às referências cadastradas (ex: "Motivo Leitmotiv", "Citação Direta").

# 📚 Especificações Detalhadas dos Casos de Uso

## 1. CU5: Cadastrar Referência Cruzada

| Seção | Detalhes |
| :--- | :--- |
| **Nome do Caso de Uso** | CU5: Cadastrar Referência Cruzada |
| **Ator Principal** | Especialista/Crítico |
| **Objetivo** | Permitir que um usuário especialista adicione um novo par de referência musical verificada ao sistema. |
| **Pré-Condição** | 1. O Ator deve estar logado no sistema como **Especialista**. <br> 2. Ambas as obras (Origem e Referência) devem estar cadastradas. |
| **Pós-Condição** | 1. Uma nova instância de `ReferenciaCruzada` é criada. <br> 2. O `statusValidacao` é definido como "Não Validada". |
| **Fluxo Principal** | 1. O Ator acessa a função de Cadastro de Referência. <br> 2. O sistema exibe o formulário de cadastro. <br> 3. O Ator seleciona a **Obra Audiovisual (Origem)** e a **Obra Referência**. <br> 4. O Ator insere a **Justificativa** detalhada da relação musical (Texto longo, obrigatório). <br> 5. O Ator pode **(Opcional)** `Adicionar Tags Técnicas` (**<<extend>> CU7**). <br> 6. O Ator confirma o cadastro. <br> 7. O sistema registra a `ReferenciaCruzada` e exibe mensagem de sucesso. |
| **Fluxo Alternativo** | **5a. Dados Incompletos:** Se o Ator tentar salvar sem Justificativa ou com obras não selecionadas, o sistema exibe uma mensagem de erro: "A Justificativa e as Obras são obrigatórias" e retorna ao passo 3. |

---

## 2. CU6: Votar e Justificar Avaliação

| Seção | Detalhes |
| :--- | :--- |
| **Nome do Caso de Uso** | CU6: Votar e Justificar Avaliação |
| **Ator Principal** | Entusiasta/Fã ou Especialista/Crítico |
| **Objetivo** | Permitir que o usuário contribua para a validação do score de uma referência cruzada existente. |
| **Pré-Condição** | 1. O Ator deve estar logado. <br> 2. A Referência Cruzada deve existir e estar disponível para votação. |
| **Pós-Condição** | 1. Um novo registro de `Voto` é criado, vinculado ao `Usuário`. <br> 2. O `scoreValidacao` da `ReferenciaCruzada` é recalculado. |
| **Fluxo Principal** | 1. O Ator visualiza uma `ReferenciaCruzada` e seus detalhes. <br> 2. O Ator seleciona o tipo de voto ("Concordo" / "Discordo"). <br> 3. O Ator pode **(Opcional)** `Adicionar um Comentário` (**<<extend>> CU8**) justificando o voto. <br> 4. O Ator confirma a submissão. <br> 5. O sistema registra o `Voto`, atualiza o score da referência e exibe a contagem atualizada. |
| **Fluxo Alternativo** | **3a. Voto Duplicado:** Se o Ator tentar votar novamente na mesma referência, o sistema pergunta: "Deseja atualizar seu voto anterior?" e, se confirmado, substitui o `Voto` existente. |

## 🗺️ Semana 2: Diagrama de Casos de Uso (UML)

O Diagrama de Casos de Uso (CU) mapeia as interações dos atores (Usuário Comum e Especialista) com o sistema.
```mermaid
graph TD
A1(Entusiasta/Fã/Pesquisador)
A2(Especialista/Crítico)

CU1([Buscar Obra Audiovisual])
CU2([Consultar Trilha Sonora Completa])
CU3([Buscar Referências e Filtrar])
CU4([Acessar Link de Comparação])
CU5([Cadastrar Referência Cruzada])
CU6([Votar e Justificar Avaliação])
CU7([Adicionar Tags Técnicas])
CU8([Justificar Voto - Comentário])

CU2 -- <<include>> --> CU1
CU3 -- <<include>> --> CU1
CU5 -- <<extend>> --> CU7
CU6 -- <<extend>> --> CU8

A1 --> CU1
A1 --> CU2
A1 --> CU3
A1 --> CU4
A1 --> CU6
A2 --> CU1
A2 --> CU2
A2 --> CU3
A2 --> CU4
A2 --> CU5
A2 --> CU6
