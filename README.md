# stratify-shared-contracts

Contratos compartilhados entre todos os serviços Stratify.
**Toda comunicação entre serviços passa pelos tipos definidos aqui.**

## Conteúdo

- `/schemas/` — JSON Schema de cada evento
- `/examples/` — Exemplos de eventos válidos em JSON
- `CHANGELOG.md` — Histórico de mudanças em schemas

## Regra de Versionamento

- **PATCH** (1.0.x): Adição de campos opcionais — backward compatible
- **MINOR** (1.x.0): Adição de novos eventos — não breaking
- **MAJOR** (x.0.0): Mudança em campos obrigatórios — breaking change — requer migração coordenada

Nunca remova campos de eventos existentes — apenas marque como `deprecated`.

## Uso por Serviço

| Serviço | Como Usa |
|---------|----------|
| stratify-core-backend (Rails) | `dry-schema` para validação |
| stratify-analysis-engine (Python) | `jsonschema` para validação de input |
| stratify-desktop-client (Tauri/Rust) | `schemars` para types gerados |
