# Scripts

Coleção de scripts Bash utilitários escritos durante os estudos.

---

## Índice

- [Exemplos](exemplos.md)

---

## Organização

| Arquivo | Descrição |
|---|---|
| `exemplos.md` | Scripts de exemplo e aprendizado |

---

## Convenções

- Todos os scripts começam com `#!/usr/bin/env bash`
- Variáveis em `UPPER_CASE` para constantes, `lower_case` para locais
- Comentário de cabeçalho em cada script: nome, descrição, uso
- Tratamento de erros com `set -euo pipefail` quando aplicável

---

## Template de Script

```bash
#!/usr/bin/env bash
# nome-do-script.sh
# Descrição: o que este script faz
# Uso: ./nome-do-script.sh [argumentos]

set -euo pipefail

# ...
```
