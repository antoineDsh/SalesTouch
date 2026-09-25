# SalesTouch

[English](../README.md) · [Français](fr.md) · [Deutsch](de.md) · [Español](es.md) · [Português](pt.md) · [Italiano](it.md)

**Prospecção no LinkedIn para agentes de IA.** O SalesTouch é um MCP do LinkedIn que conecta o Claude à pesquisa de prospects, conversas, mensagens, publicações, acompanhamentos e filas. O SalesTouch não é afiliado nem endossado pelo LinkedIn.

## Requisitos

Um espaço de trabalho SalesTouch com plano ativo e conta do LinkedIn conectada. Os recursos do Sales Navigator exigem os acessos correspondentes. Os resultados dependem das permissões, dos dados disponíveis e dos limites da plataforma.

## Instalar no Claude Code

Execute no Claude Code:

```text
/plugin marketplace add antoineDsh/SalesTouch
/plugin install salestouch@salestouch
```

Reinicie o Claude Code, execute `/mcp`, selecione SalesTouch e autorize a conexão no navegador. Nunca coloque sua senha do LinkedIn, cookies ou chaves de API na conversa ou na configuração do plugin.

## Instalar no Claude Desktop ou Cowork

Abra **Customize → Plugins**. Em **Personal plugins**, selecione **+ → Add marketplace**, escolha a opção de repositório e digite `antoineDsh/SalesTouch`. Instale e ative `salestouch` e autorize o conector SalesTouch. As opções disponíveis dependem do seu plano Claude e das configurações da organização.

## Três prompts para começar

1. “Liste minhas contas do LinkedIn conectadas com o SalesTouch.”
2. “Pesquise este perfil do LinkedIn e suas publicações recentes. Escreva uma apresentação relevante sem enviá-la: [URL do perfil].”
3. “Leia esta conversa do LinkedIn, resuma as necessidades do prospect e prepare uma resposta sem enviá-la: [ID da conversa ou URL do perfil].”

Substitua os valores entre colchetes pelos seus alvos. Você também pode extrair resultados de busca ou pessoas que interagiram com publicações, percorrer resultados salvos e baixar exportações. Confira destinatário, conteúdo e horário antes de aprovar uma ação. Pendente não significa entregue. Consulte a fila antes de repetir uma operação de escrita.

## Conexão e ajuda

O endpoint MCP remoto é `https://www.salestouch.io/api/mcp`, com Streamable HTTP e OAuth. Se a autorização falhar, reconecte o conector, confira o espaço de trabalho e a conexão do LinkedIn e repita o prompt das contas. Compartilhe com o suporte apenas um código de erro e passos para reprodução, sem credenciais, tokens ou mensagens privadas.

[Configuração](../SETUP.md) · [Suporte](https://www.salestouch.io/support) · [Segurança](../SECURITY.md) · [Documentação](https://www.salestouch.io/docs) · [Privacidade](https://www.salestouch.io/privacy) · [Termos](https://www.salestouch.io/terms) · [support@salestouch.io](mailto:support@salestouch.io)

Os arquivos do plugin usam a [licença MIT](../LICENSE). O backend hospedado é proprietário.

## Versão 0.9.2

Conexão com o Claude Code corrigida: apenas as permissões necessárias para o MCP são solicitadas.

## Versão 0.9.1

Instalação atualizada em seis idiomas; configuração e suporte incluídos no pacote; analytics técnicos do MCP sem objetivos de conversa nem conteúdo das chamadas. [Histórico de alterações](../CHANGELOG.md).
