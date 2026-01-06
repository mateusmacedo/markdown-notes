# 001 - Escolha de Formato Markdown para Documentação

**Data**: 2026-01-06  
**Status**: Aceito  
**Autores**: Equipe de Documentação

## Contexto

Precisamos definir um formato padrão para documentação técnica que seja:
- Versionável em Git
- Fácil de escrever e ler
- Suporte a diagramas e código
- Independente de ferramentas proprietárias

## Decisão

Adotaremos Markdown (.md) como formato padrão para toda documentação técnica, com suporte a:
- Markdown padrão (CommonMark)
- Mermaid para diagramas embutidos
- Blocos de código com syntax highlighting

## Alternativas Consideradas

### Alternativa 1: Wiki (Confluence/Notion)

**Prós:**
- Interface visual amigável
- Recursos de colaboração integrados
- Busca avançada

**Contras:**
- Não versionável com Git
- Dependência de ferramentas externas
- Dificulta revisão de código
- Custo adicional

### Alternativa 2: LaTeX

**Prós:**
- Formatação profissional
- Excelente para documentos longos

**Contras:**
- Curva de aprendizado alta
- Complexo para documentação simples
- Menos legível em formato texto

## Consequências

### Positivas

- Documentação versionada junto com código
- Facilita revisão através de Pull Requests
- Suporte nativo no GitHub/GitLab
- Ferramentas de edição amplamente disponíveis

### Negativas

- Formatação visual menos rica que wikis
- Diagramas complexos podem ser difíceis em Mermaid

### Neutras

- Requer aprendizado básico de Markdown
- Necessário escolher convenções de organização

## Riscos

- **Risco**: Documentos muito grandes podem ser difíceis de navegar
  - **Mitigação**: Dividir em múltiplos arquivos e usar links
- **Risco**: Diagramas complexos podem ser limitados
  - **Mitigação**: Usar Mermaid para diagramas simples e exportar imagens para complexos

## Links e Referências

- [Markdown Guide](https://www.markdownguide.org/)
- [Mermaid Documentation](https://mermaid.js.org/)
- [CommonMark Spec](https://commonmark.org/)

## Notas Adicionais

Esta decisão não impede o uso de outras ferramentas para diagramação complexa (como Draw.io), mas elas devem ser exportadas e incluídas no repositório.

---

## Histórico de Revisões

| Data | Mudança | Autor |
|------|---------|-------|
| 2026-01-06 | Criação inicial | Equipe de Documentação |
