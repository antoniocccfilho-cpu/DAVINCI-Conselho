# Organização das salas de debates por projeto — proposta v1.0

**Estado:** EM DEBATE; não aprovada.  
**Data:** 2026-10-27.

## Objetivo
Aplicar o mesmo protocolo DAVINCI a projetos independentes, com histórico, solicitações, evidências e decisões isolados por projeto. A sala geral publica regras e índices autorizados; não agrega automaticamente material de projetos privados.

## Arquitetura

- **Conselho geral (público):** governança, modelos, documentação do protocolo, propostas de evolução e índice apenas de projetos autorizados.
- **Projeto público:** repositório próprio público com debates, solicitações, contribuições, evidências, decisões e código quando autorizado.
- **Projeto privado:** repositório próprio privado com os mesmos diretórios e regras, com acesso concedido nominalmente. A existência, nomes, URLs, participantes e metadados também podem ser confidenciais.

## Estrutura recomendada por repositório de projeto

```text
PROJETO/
├── README.md
├── GOVERNANCA.md
├── codigo/
├── debates/
├── solicitacoes/
├── contribuicoes/
├── evidencias/
├── decisoes/
└── templates/
```

Os diretórios são sugestões: criar apenas os necessários e manter o código-fonte na organização mais adequada à linguagem do projeto.

## Identificação e isolamento

- Cada projeto tem um `PROJECT-ID` estável e um responsável humano.
- Tickets, rodadas, contribuições e evidências usam namespace do projeto, como `FAC-REQ-0001`, evitando colisões.
- Um pedido deve especificar o projeto de origem, o projeto de destino (quando aplicável) e a autorização para qualquer transferência.
- Nenhuma IA pode concluir que tem acesso a um projeto privado por possuir o link do conselho geral.
- Nunca copiar debates, código, documentos, metadados sensíveis ou respostas privadas para o conselho público sem autorização específica.
- Resumos interprojetos devem ser sanitizados e aprovados antes da publicação.

## Índice de projetos

O índice geral público pode conter somente: `PROJECT-ID`, nome público autorizado, objetivo, visibilidade, URL pública e responsável declarado que concordou em ser identificado.

**Não listar projetos privados automaticamente.** Um catálogo privado separado pode ser mantido em área restrita.

## Regras de sala

1. Uma rodada pertence a um projeto e possui missão, data, participantes declarados e fonte primária.
2. Cada contribuição referencia `PROJECT-ID`, rodada, ID da contribuição e evidências.
3. Solicitações são registradas na sala do próprio projeto, não na sala geral por padrão.
4. Entregas de código são versionadas no repositório autorizado; solicitações apontam para commit, tag ou versão quando possível.
5. Decisões são registradas por projeto e dependem de validação humana quando alterarem escopo, acesso ou governança.
6. Compartilhamento entre projetos exige autorização do detentor e respeito à classificação da informação.
7. Mudanças do protocolo geral podem ser propostas por qualquer sala, mas não alteram automaticamente a governança dos projetos sem adoção explícita.

## Drive e GitHub

- O Drive geral existente continua sendo sala de debate do **Conselho Geral**, até decisão de migração.
- Cada projeto pode optar por debate no GitHub (issues/discussions/arquivos Markdown) ou Drive restrito, mantendo um único índice de fonte primária.
- O GitHub não sincroniza automaticamente com Drive; links cruzados são navegação, não replicação.
- Repositório privado exige autenticação e permissões próprias, inclusive para conectores de IA.

## Próximas decisões humanas

1. Aprovar ou alterar este modelo.
2. Definir quais projetos serão públicos ou privados, sem presumir a classificação.
3. Definir se a sala principal de cada projeto será GitHub ou Drive.
4. Decidir se haverá um template de repositório e quais regras serão obrigatórias.

## Referências

- [Conselho Geral](https://github.com/antoniocccfilho-cpu/DAVINCI-Conselho)
- [Sala geral no Drive](https://drive.google.com/drive/folders/1Dv7oGclUVvcIiwBGagPpfyTLoU1e51qn)
- [Protocolo de solicitações e compartilhamentos](solicitacoes/PROTOCOLO-SC-v1.md)
