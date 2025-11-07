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
