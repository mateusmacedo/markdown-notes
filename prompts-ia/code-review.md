# Code Review com IA

**Categoria**: Desenvolvimento  
**Criado em**: 2026-01-06  
**Última atualização**: 2026-01-06  
**Autor**: Equipe de Desenvolvimento

## Objetivo

Realizar revisão de código automatizada usando IA para identificar problemas de qualidade, bugs potenciais, e sugestões de melhoria antes da revisão humana.

## Quando Usar

- Antes de submeter um Pull Request
- Ao refatorar código legado
- Para validar mudanças críticas
- Como parte do CI/CD pipeline

## Contexto Necessário

- Linguagem de programação utilizada
- Tipo de código (backend, frontend, biblioteca, etc.)
- Contexto do projeto (propósito do código)
- Padrões e convenções do projeto

## Prompt

```
Por favor, revise o seguinte código {LINGUAGEM} e forneça feedback sobre:

1. **Qualidade do Código**:
   - Legibilidade e clareza
   - Aderência a padrões da linguagem
   - Naming conventions
   - Complexidade

2. **Bugs e Problemas**:
   - Bugs potenciais
   - Edge cases não tratados
   - Erros lógicos
   - Vazamentos de recursos

3. **Performance**:
   - Operações ineficientes
   - Uso excessivo de memória
   - Possíveis otimizações

4. **Segurança**:
   - Vulnerabilidades potenciais
   - Validação de entrada
   - Tratamento de erros

5. **Melhores Práticas**:
   - Design patterns aplicáveis
   - SOLID principles
   - DRY violations

Código:
```{LINGUAGEM}
{CODIGO}
```

Contexto do projeto: {CONTEXTO}

Forneça sugestões específicas com exemplos de código quando apropriado.
```

## Exemplo de Uso

### Input

```
Por favor, revise o seguinte código JavaScript e forneça feedback sobre:

[... lista de pontos ...]

Código:
```javascript
function calculateTotal(items) {
    let total = 0;
    for (var i = 0; i < items.length; i++) {
        total = total + items[i].price * items[i].quantity;
    }
    return total;
}
```

Contexto do projeto: E-commerce checkout system
```

### Output Esperado

```
Análise do código:

1. **Qualidade do Código**: ✓ Boa
   - Função clara e focada
   - Sugestão: Use `const` em vez de `var`
   - Sugestão: Use métodos de array modernos (reduce)

2. **Bugs e Problemas**: ⚠️
   - Não valida se items é array
   - Não verifica se price/quantity existem
   - Pode resultar em NaN

3. **Performance**: ✓ Adequada
   - Para arrays pequenos, está ok
   - Para arrays grandes, considere otimizações

[... mais feedback ...]

Código sugerido:
```javascript
function calculateTotal(items) {
    if (!Array.isArray(items)) return 0;
    
    return items.reduce((total, item) => {
        const price = Number(item?.price) || 0;
        const quantity = Number(item?.quantity) || 0;
        return total + (price * quantity);
    }, 0);
}
```
```

## Variações

### Variação 1: Review Focado em Segurança

Para análise focada em segurança, adapte o prompt:

```
Analise o seguinte código {LINGUAGEM} focando em aspectos de SEGURANÇA:

1. Vulnerabilidades conhecidas (OWASP Top 10)
2. Validação e sanitização de entrada
3. Tratamento de dados sensíveis
4. Autorização e autenticação
5. Exposição de informações

[... resto do prompt ...]
```

### Variação 2: Review Focado em Performance

Para otimização de performance:

```
Analise o seguinte código {LINGUAGEM} focando em PERFORMANCE:

1. Complexidade algorítmica (Big O)
2. Uso de memória
3. Operações bloqueantes
4. Caching e memoization
5. Database queries (N+1 problems)

[... resto do prompt ...]
```

## Dicas de Uso

- **Dica 1**: Forneça contexto adequado do projeto para sugestões mais relevantes
- **Dica 2**: Revise código em chunks pequenos (< 200 linhas) para melhor análise
- **Dica 3**: Combine com ferramentas de linting automático para melhores resultados
- **Dica 4**: Use a revisão de IA como primeira passada, não substitui revisão humana

## Limitações

- **Limitação 1**: Pode não entender contexto complexo do domínio de negócio
- **Limitação 2**: Pode sugerir over-engineering para código simples
- **Limitação 3**: Não substitui testes automatizados e validação de requisitos

## Prompts Relacionados

- [Refactoring de Código](refactoring-code.md) - Para melhorias após review
- [Documentação de Código](code-documentation.md) - Para documentar código revisado

## Referências

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Clean Code Principles](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [SOLID Principles](https://en.wikipedia.org/wiki/SOLID)

## Notas Adicionais

Este prompt funciona melhor com modelos de IA especializados em código (como GPT-4, Claude, ou GitHub Copilot).

---

## Histórico de Versões

| Data | Versão | Mudança | Autor |
|------|--------|---------|-------|
| 2026-01-06 | 1.0 | Criação inicial | Equipe de Desenvolvimento |
