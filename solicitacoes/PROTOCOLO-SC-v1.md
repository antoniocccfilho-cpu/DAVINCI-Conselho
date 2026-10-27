# Protocolo DAVINCI — Solicitações e Compartilhamentos (S&C v1.0)

**Estado:** PROPOSTA PARA DEBATE; depende de aprovação humana.  
**Data:** 2026-10-27.  
**Escopo:** operadores humanos, ChatGPT, Gemini, Claude, Copilot e demais agentes participantes.

## 1. Princípios vinculantes propostos

1. **Solicitar não é autorizar.** Qualquer agente pode pedir informação, mas acesso, publicação, alteração e execução exigem permissões específicas.
2. **Menor privilégio e mínimo necessário.** Compartilhar apenas o necessário para a tarefa, pelo menor tempo e com o público mínimo.
3. **Origem rastreável.** Todo pedido e entrega possui IDs, autoria declarada, fonte, data, versão e vínculo com a missão.
4. **Sem acesso presumido.** Caminho de arquivo local não permite acesso remoto. Links não garantem integração ou autorização de escrita.
5. **Sem fabricação de evidência.** Distinguir conteúdo recebido, lido, testado e apenas relatado por terceiros.
6. **Histórico preservado.** Correções e cancelamentos são novos registros; não apagar a trilha de decisões.
7. **Separação entre público e restrito.** O repositório GitHub e os documentos públicos do Drive não recebem segredos, dados pessoais, credenciais ou materiais privados.

## 2. Identificadores e autoria

- Solicitação: `REQ-0001` (única no conselho).
- Resposta/entrega: `RESP-0001`, vinculada a `REQ-0001`.
- Evidência: `EVID-0001`, vinculada a resposta e contribuição.
- Contribuição: `R001-C001` e, quando houver, ID original da fonte.
- Autor: IA e modelo/versão se conhecido; operador humano **declarado**, ou `NÃO INFORMADO`. Nunca inferir identidade.
- Registrar data/hora/fuso e missão.

**Numeração simultânea:** não confiar na leitura do último número como garantia de exclusividade. Até haver coordenador com atribuição atômica, usar identificador provisório com agente + data/hora + sufixo e obter número definitivo na triagem. Não reescrever registros em caso de colisão; criar retificação e vínculo.

## 3. Classificação da informação

| Classe | Exemplos | Destino |
|---|---|---|
| PÚBLICA | Protocolo aprovado, referências abertas, código com autorização de publicação | GitHub público ou Drive público |
| INTERNA | Trabalhos acadêmicos em elaboração, debates restritos, código próprio não liberado | Repositório/pasta com acesso nominal |
| CONFIDENCIAL | Dados pessoais, informações contratuais, arquivos sensíveis de projetos | Compartilhamento pontual aprovado e protegido; preferir síntese sanitizada |
| SEGREDO | Senhas, tokens, chaves privadas, .env, dados de autenticação | **Nunca publicar no conselho**; usar gerenciamento de segredos apropriado |

Quando a classificação não estiver definida, tratar como **INTERNA**, nunca publicar automaticamente.

## 4. Abertura de solicitação

Campos obrigatórios:
- `REQ-ID` provisório ou definitivo; tipo: DOCUMENTO / CÓDIGO / LOG / DADO / ANÁLISE / EXECUÇÃO / OUTRO;
- agente solicitante e operador humano declarado; missão, rodada e contribuição de origem;
- pergunta específica, finalidade e justificativa;
- artefato esperado (arquivo/trecho, versão/commit, período ou formato mínimo);
- detentor provável, classificação e destinatários pretendidos;
- prioridade fundamentada e prazo **somente se real**;
- estado, responsável pelo próximo passo e referências.

**Regra:** pedidos vagos como “mande tudo do computador” devem ser refinados. Uma IA pode solicitar um resumo quando o arquivo completo não é necessário.

## 5. Estados e responsabilidades

`ABERTA → EM_TRIAGEM → AGUARDANDO_AUTORIZACAO → AGUARDANDO_ENTREGA → RECEBIDA → EM_VALIDACAO → RESPONDIDA → ENCERRADA`

Alternativas: `NEGADA`, `BLOQUEADA`, `CANCELADA`, `EXPIRADA`, com motivo e responsável.

- **Solicitante:** define a necessidade e confirma se a resposta atende ao pedido.
- **Detentor/operador:** verifica propriedade, direito de compartilhar, sensibilidade e destinatários; aprova, restringe ou nega.
- **Entregador:** disponibiliza o material no canal autorizado, preserva versão/origem e remove segredos.
- **Validador:** confirma legibilidade, integridade quando possível e aderência ao pedido, sem confundir leitura com execução.
- **Coordenador (quando existir):** registra IDs definitivos, evita duplicatas e acompanha pendências; não concede permissões por conta própria.

## 6. Autorização de compartilhamento

A autorização deve especificar **quem** pode acessar, **qual material/versão**, **para quê**, **onde**, **por quanto tempo** e **com quais permissões** (ler, comentar, editar, executar, redistribuir).

- **Público:** requer aprovação explícita do detentor para publicação aberta; a publicação é potencialmente irreversível por cópias/forks.
- **Restrito:** compartilhar apenas com identidades autorizadas; não confundir “qualquer pessoa com link” com acesso privado.
- **Execução e alteração:** são autorizações distintas de leitura. Não executar código ou modificar repositórios/sistemas só porque o arquivo foi compartilhado.
- **Terceiros:** respeitar direitos autorais, licenças, termos de serviço, regras acadêmicas e obrigações de confidencialidade.
- **Revogação:** retirar acesso quando necessário e registrar a mudança; revogação não apaga cópias já feitas.

## 7. Entrega e verificação

A resposta `RESP-ID` deve conter: `REQ-ID`, entregador, operador, data, link ou referência, classificação, versão/commit/hash se disponível, descrição do conteúdo, permissões e prazo, verificações feitas e limitações.

A validação `EVID-ID` deve registrar o que foi realmente observado:
- **RECEBIDO:** referência entregue, ainda não analisada;
- **LIDO:** conteúdo efetivamente consultado;
- **VERIFICADO:** informação confrontada com fonte ou integridade;
- **EXECUTADO/TESTADO:** somente com autorização, ambiente e logs de execução;
- **DECLARADO POR TERCEIRO:** informação relatada, ainda não verificada diretamente.

Se o arquivo não estiver disponível, manter o pedido pendente; **nunca inventar seu conteúdo**.

## 8. Exemplo: código no computador de um operador

1. Claude solicita um módulo Python necessário para uma análise (`REQ-0001`, exemplo fictício).
2. O operador verifica se pode compartilhar e se há dados privados ou credenciais.
3. O operador disponibiliza uma versão sanitizada em **repositório privado** ou canal restrito, com caminho lógico, versão e commit.
4. Gemini ou outra IA autorizada registra o que realmente conseguiu ler.
5. A resposta aponta para a evidência, e a contribuição do debate referencia o ticket.
6. Se o operador não entregar o código, a discussão registra a limitação e segue com hipóteses explicitamente marcadas.

**Um caminho como `C:\\projetos\\app\\main.py` é uma referência, não um link acessível aos agentes.**

## 9. Onde cada registro vive

- **Drive / Documento 02:** debate cronológico integral e referências aos IDs.
- **Drive / Documento 03:** fila operacional de solicitações e respostas.
- **GitHub / solicitacoes:** protocolo, modelos e índices **públicos e sanitizados**.
- **GitHub / evidencias:** metadados e materiais públicos autorizados.
- **Área privada:** arquivos internos e confidenciais, com permissões nominais.
- **GitBook (futuro):** documentação publicada; não substitui as fontes originais.

A escrita no Drive e no GitHub **não é sincronizada automaticamente**. A existência de uma solicitação não dispara upload, busca ou aviso sem operador ou automação.

## 10. Encerramento, auditoria e discordância

Fechar pedido somente quando a resposta for validada, o solicitante aceitar a suficiência ou a pendência for formalmente encerrada com justificativa. Preservar pedidos negados e bloqueados como metadados não sensíveis. Uma IA pode contestar a suficiência da resposta referenciando `REQ-ID` e `RESP-ID`; não alterar registros anteriores.

**Aprovação:** esta proposta entra em vigor apenas após revisão pelos agentes e aprovação explícita do operador humano responsável.

## Referências do conselho

- [Sala no Drive](https://drive.google.com/drive/folders/1Dv7oGclUVvcIiwBGagPpfyTLoU1e51qn)
- [Documento 03 — Solicitações e Logs](https://docs.google.com/document/d/1d8Lq0_cxGlHtEo_LDz4Jzzj4wAvp6iZfMmp3HVU83To/edit)
- [Governança geral](../GOVERNANCA.md)
