# PowerVersion

🤖 Git Source Versioning Agent

    Um agente de IA focado em análise de diffs, geração de commits atômicos e documentação automatizada (Docs as Code).

O Git Source Versioning Agent não é apenas um gerador de mensagens de commit. É uma skill universal (System Prompt) desenhada para atuar em ferramentas de IA via terminal (como OpenCode e Claude Code) ou IDEs modernas (como Cursor). Seu propósito é padronizar o histórico do repositório, garantindo que cada alteração de código seja minuciosamente documentada e rastreável.
✨ Principais Funcionalidades

    🛡️ Segurança Git Rigorosa (Push Block): O agente opera em um ambiente contido. Ele é estritamente proibido de executar ou sugerir qualquer comando de sincronização remota (como git push). Todo o processo ocorre localmente, garantindo que o desenvolvedor tenha a palavra final antes da publicação.

    🧩 Commits Atômicos: Força a regra de "Um arquivo = Um commit independente". Nada de agrupar dezenas de alterações desconexas em um único pacote.

    👤 Identidade Humana Pura: O agente consulta dinamicamente as credenciais do Git local (git config user.name e user.email). É blindado contra assinaturas de IA, garantindo que o histórico de autoria permaneça limpo e sem tags como Co-authored-by.

    📝 Padrão Conventional Commits: Todas as mensagens são geradas utilizando o padrão v1.0.0 (ex: feat(auth): ..., fix(api): ...), facilitando a leitura e a geração de releases futuros.

    🗂️ Ecossistema Docs as Code: Ao analisar uma alteração, o agente gera automaticamente um arquivo de changelog individual na pasta docs/changelogs/ com um comparativo visual detalhado, registrando o histórico de impacto de forma independente.

⚙️ Como Funciona o Pipeline

O fluxo de trabalho do agente é otimizado para atuar em lote sobre o seu workspace:

    Varredura: Lê os arquivos na sua staging area ou os diffs enviados.

    Classificação: Etiqueta cada arquivo como 🟩 NOVO, 🟨 MODIFICADO ou 🟥 DELETADO.

    Análise de Hunks: Destrincha cada bloco de código alterado, calculando linhas adicionadas/removidas e explicando o impacto lógico (aditivo, substitutivo ou destrutivo).

    Entrega: Gera os comandos de commit locais e redige a documentação consolidada no terminal.

🚀 Compatibilidade

Este agente é formatado em Markdown e desenhado para ser agnóstico, funcionando em:

    Terminais e CLIs: OpenCode, Claude Code, Antigravity.

    IDEs via Regras de Workspace: Cursor (via .cursorrules), VS Code (via extensões nativas de chat).
