# Coletor de Evidências Audiovisuais

**Versão:** V3 — identificação temporal de entrevistados (corrigida)  
**Arquivo principal:** `Coletor_Evidencias_Entrevistados_v3_corrigido.html`  
**Idioma:** Português (Brasil)  
**Finalidade:** apoio ao registro e à organização de evidências audiovisuais em trabalhos acadêmicos, TCCs e pesquisas documentais.

## Sobre o aplicativo

Aplicativo executado no navegador para registrar metadados de vídeos do YouTube, inserir ou tentar recuperar legendas, estruturar uma transcrição em janelas de tempo e associar trechos narrados a entrevistados identificados pelo pesquisador. Permite exportar os resultados para Word (`.doc`) e texto (`.txt`).

A **V3** preserva os módulos da versão original e acrescenta um cadastro recolhível de entrevistados, com múltiplos períodos de narrativa por participante. Também corrige a leitura de timestamps como `06m 40s`, além de `06:40`.

## Funcionalidades

- Registro de URL, título, canal, data de publicação, duração e descrição do vídeo.
- Tentativa de preenchimento automático dos metadados a partir de serviços externos.
- Entrada manual de transcrição e tentativa de leitura de legendas públicas.
- Organização da transcrição em blocos de **30, 60, 120, 180 ou 300 segundos**.
- Cadastro de diversos entrevistados pelo botão **+ Entrevistado**.
- Recolhimento/expansão de cada cadastro, exibindo o nome no cabeçalho.
- Cadastro de mais de um intervalo de fala por pessoa pelo botão **+ Narrativa (novo período de fala)**.
- Associação dos nomes às marcações temporais da transcrição e indicação dos participantes relacionados a cada bloco.
- Ficha de auditoria, sugestão de referência bibliográfica ABNT e comandos para copiar informações.
- Exportação de relatórios com identificação de participantes e períodos de fala.

## Como executar

1. Coloque `Coletor_Evidencias_Entrevistados_v3_corrigido.html` em uma pasta do computador.
2. Abra o arquivo em um navegador atualizado (por exemplo, Edge ou Chrome). Não é necessária instalação ou servidor local para abrir a interface.
3. Mantenha acesso à internet para carregar o Tailwind CSS e a fonte Inter. As buscas automáticas de metadados e legendas também dependem da internet e de serviços de terceiros.

> A página HTML pode abrir localmente, mas a recuperação automática de conteúdo do YouTube **não é garantida**. Se ela falhar, preencha os metadados e cole a transcrição manualmente.

## Fluxo de uso

### 1. Registrar a fonte

Cole o link do vídeo do YouTube e clique em **Obter**. Confira e complete o título, o canal, a data de publicação, a duração e a descrição. Se necessário, preencha todos esses campos manualmente.

### 2. Inserir a transcrição

Cole a transcrição no campo **Entrada de Transcrição** ou tente o botão **Ler automaticamente**. Escolha o intervalo de agrupamento temporal, que é de **60 segundos por padrão**, e clique em **Estruturar Transcrição em Blocos**.

Use, preferencialmente, transcrições com um horário no início de cada linha, como:

```text
06:35 Nossa experiência começou com atividades no viveiro.
06:45 A participação das mulheres fortaleceu o trabalho coletivo.
07:06 As oficinas também envolveram a comunidade.
```

A V3 reconhece também os formatos `06m 45s` e `01h 06m 45s` no início das linhas. **Textos sem timestamps confiáveis não permitem identificar com precisão a posição de cada fala no vídeo.**

### 3. Cadastrar entrevistados

Na seção **Entrevistas · Identificação das Narrativas**:

1. Digite o nome ou código de identificação da primeira pessoa.
2. Informe o **Início** e o **Fim** de seu período de fala, usando `mm:ss` ou `hh:mm:ss`.
3. Clique em **+ Narrativa** para registrar outra fala da mesma pessoa.
4. Clique em **+ Entrevistado** para incluir outra pessoa.
5. Clique no cabeçalho de um entrevistado para recolher ou expandir seu cadastro.

**Exemplo ilustrativo:**

| Entrevistado | Início | Fim |
|---|---:|---:|
| Vilma Martins | 00:01 | 06:37 |
| Kelly Cristina | 06:40 | 08:17 |
| Bruna | 08:18 | 09:10 |
| Vilma Martins | 09:21 | 11:14 |

Os nomes e horários acima são apenas exemplos de preenchimento; devem ser conferidos no vídeo utilizado na pesquisa.

### 4. Conferir a associação das falas

A visualização estruturada passa a indicar o nome da pessoa associada ao horário de um fragmento, quando existe uma correspondência inequívoca entre o timestamp da transcrição e o intervalo cadastrado. O cabeçalho do bloco também pode apresentar os participantes cujas janelas de fala cruzam aquele intervalo.

Exemplo de apresentação:

```text
06m 00s – 07m 00s — Vilma Martins / Kelly Cristina
06m 45s — Kelly Cristina: A participação das mulheres fortaleceu o trabalho coletivo.

07m 00s – 08m 00s — Kelly Cristina
07m 06s — Kelly Cristina: As oficinas também envolveram a comunidade.
```

**A identificação não utiliza reconhecimento de voz.** É uma associação feita com base nos intervalos inseridos pelo pesquisador. Períodos de pessoas diferentes que se sobrepõem geram aviso e ficam sem atribuição inequívoca no trecho conflitante. Revise as transições de fala, os horários e a integridade do texto antes de usar o material academicamente.

### 5. Exportar o relatório

Após estruturar a transcrição, use:

- **Exportar Relatório em Word:** gera um arquivo **`.doc`**, composto de HTML compatível com o Word; **não é um `.docx` nativo**.
- **Exportar Arquivo em Texto:** gera um arquivo **`.txt`** em UTF-8.

Os relatórios incluem metadados, descrição, sugestão ABNT, cadastro de entrevistados e respectivos períodos de narrativa, além da transcrição estruturada. A associação de nomes é aplicada aos fragmentos temporais elegíveis.

## Cuidados metodológicos

- Confira nomes, autoria, data de publicação, citação ABNT e horários na fonte original.
- A transcrição automática, quando disponível, pode conter erros, omissões ou pontuação imprecisa.
- Atribuição temporal **não equivale à comprovação de identidade do locutor**; a validação depende da escuta e da documentação do pesquisador.
- Respeite consentimentos, acordos de pesquisa, direitos de imagem/voz e regras de proteção de dados pessoais. Use códigos ou pseudônimos quando apropriado.
- Preserve cópia da fonte, identificação do vídeo, data de consulta e decisões de transcrição para permitir auditoria acadêmica.

## Limitações técnicas conhecidas

1. **Persistência:** o aplicativo mantém os dados apenas na memória da página. Fechar/recarregar a aba ou trocar de vídeo pode eliminar os registros preenchidos. **Exporte o relatório antes de encerrar a sessão.**
2. **Busca automática:** usa serviços externos, sujeitos a falhas, mudanças de API e bloqueios de CORS.
3. **Conectividade:** o rótulo da interface sobre processamento local não significa que todas as funções sejam offline; solicitações de metadados e legendas são enviadas a serviços externos.
4. **Precisão das narrativas:** depende de timestamps válidos e de intervalos de fala fornecidos pelo pesquisador. O sistema não transcreve áudio por reconhecimento de voz local, nem identifica automaticamente quem está falando.
5. **Exportação Word:** o download é `.doc` baseado em HTML, não `.docx` verdadeiro.
6. **Validação:** a conferência do código e da associação temporal não substitui um teste integral no navegador com um vídeo real e a abertura dos arquivos exportados.

## Arquivos sugeridos para distribuição

```text
Coletor-Evidencias-Audiovisuais/
├── Coletor_Evidencias_Entrevistados_v3_corrigido.html
└── README.md
```

Para publicação no GitHub Pages, o arquivo principal pode ser renomeado para `index.html`, **sem alterar seu conteúdo**, mantendo o `README.md` na raiz do repositório.

## Histórico resumido

| Versão | Descrição |
|---|---|
| Original | Metadados, transcrição por blocos, sugestão ABNT e exportação. |
| V2 | Cadastro recolhível de entrevistados e múltiplas janelas de narrativa. |
| V3 corrigida | Correção do reconhecimento de marcadores `mm:ss`, `hh:mm:ss` e `06m 40s` e associação temporal de participantes na visualização e nos relatórios. |

---

**Uso acadêmico:** ferramenta de apoio à organização de fontes e evidências. A responsabilidade pela validação documental, transcrição e interpretação das narrativas permanece com o pesquisador.
