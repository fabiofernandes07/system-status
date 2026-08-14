# SystemStatusBanner

Banner de aviso no topo da aplicação, controlado remotamente via um JSON hospedado no GitHub (`schief-ai/system-status`).

## Onde editar

Arquivo: `status.json` no repositório [schief-ai/system-status](https://github.com/schief-ai/system-status), branch `main`.

O componente busca esse arquivo a cada carregamento da página (sem cache, via `?t=timestamp`).

## Campos

| Campo      | Tipo      | Obrigatório | Descrição                                                        |
|------------|-----------|-------------|--------------------------------------------------------------------|
| `active`   | boolean   | sim         | Se `false`, o banner não aparece.                                   |
| `message`  | string    | sim         | Texto exibido no banner.                                            |
| `severity` | string    | não         | Um de: `warning`, `danger`, `info`, `solid-danger`. Default: `warning`. |

## Severidades

| Severity        | Cor              | Ícone   | Pulso | Pode fechar? |
|-----------------|------------------|---------|-------|--------------|
| `warning`       | amarelo          | warning | sim   | sim          |
| `info`          | azul             | info    | não   | sim          |
| `danger`        | vermelho claro   | danger  | não   | não          |
| `solid-danger`  | vermelho sólido  | danger  | sim   | não          |

## Exemplo

```json
{
  "active": true,
  "message": "Estamos com instabilidade no login. Equipe já está atuando.",
  "severity": "danger"
}
```

Para desativar o banner, basta setar `"active": false`.
