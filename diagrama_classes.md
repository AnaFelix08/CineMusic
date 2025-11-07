```mermaid
classDiagram
    direction LR

    class Usuario {
        - int id
        - string nome
        - string email
        - string tipo (Especialista/Comum)
        + logar(): void
        + cadastrarReferencia(ref: ReferenciaCruzada): void
        + votar(ref: ReferenciaCruzada, tipo: string): void
    }

    class ObraAudiovisual {
        - int id
        - string titulo
        - int ano
        - string trechoMusicalLink
        + buscarReferencias(): List<ReferenciaCruzada>
    }
    
    class ObraReferencia {
        - int id
        - string titulo
        - string compositor
        - string trechoMusicalLink
    }

    class ReferenciaCruzada {
        - int id
        - string justificativa
        - date dataCadastro
        - int scoreValidacao
        - string statusValidacao (Nao Validada/Validada/Em Discussao)
        + calcularStatusValidacao(): void
        + aplicarTag(tag: Tag): void
    }

    class Voto {
        - int id
        - string tipo (Concordo/Discordo)
        - date dataVoto
        + registrarVoto(): void
    }
    
    class Comentario {
        - int id
        - string texto
        - date dataComentario
        + adicionarComentario(): void
    }
    
    class Tag {
        - int id
        - string nome
        + getReferenciasPorTag(): List<ReferenciaCruzada>
    }

    % RELACIONAMENTOS (Associações e Multiplicidade)
    Usuario "1" -- "0..*" ReferenciaCruzada : Cadastra
    Usuario "1" -- "0..*" Voto : Realiza
    Usuario "1" -- "0..*" Comentario : Escreve
    
    ReferenciaCruzada "1" -- "*" Voto : Recebe
    ReferenciaCruzada "1" -- "0..*" Comentario : Possui
    ReferenciaCruzada "*" -- "*" Tag : Classificada por
    
    ReferenciaCruzada "*" -- "1" ObraAudiovisual : Pertence a
    ReferenciaCruzada "*" -- "1" ObraReferencia : Baseada em
