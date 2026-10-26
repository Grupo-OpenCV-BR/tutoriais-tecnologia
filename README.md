# OpenCVismo — Visão Computacional

Tutoriais, trilhas de estudo e recursos da comunidade [OpenCVismo Brasil no Telegram](https://t.me/opencvBrasil), construídos com [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Desenvolvimento local

Instale o [uv](https://docs.astral.sh/uv/getting-started/installation/) e execute na raiz do projeto:

```bash
uv python install
uv sync --locked
uv run --locked mkdocs serve
```

Abra <http://127.0.0.1:8000>. O servidor recarrega o site ao editar os arquivos em `docs/` ou a configuração `mkdocs.yml`.

O projeto usa Python 3.13, definido em `.python-version` e `pyproject.toml`. O uv cria o ambiente `.venv/` e instala as versões registradas em `uv.lock`. Não é necessário ativar o ambiente manualmente.

## Validar antes de enviar

```bash
uv run --locked mkdocs build --strict
```

O site gerado fica em `site/`, que não deve ser versionado. O modo estrito interrompe a geração se houver avisos de configuração ou links quebrados.

## Atualizar dependências

As dependências diretas ficam em `pyproject.toml`; suas versões resolvidas e dependências transitivas ficam em `uv.lock`.

```bash
uv lock --upgrade
uv sync --locked
uv run --locked mkdocs build --strict
```

Ao alterar dependências, inclua o `uv.lock` atualizado no mesmo commit. Para adicionar uma dependência, use `uv add nome-do-pacote` e valide novamente a geração.

## Como contribuir

1. Faça um fork e crie uma branch para suas alterações.
2. Edite o conteúdo em `docs/` e atualize a navegação em `mkdocs.yml`, se necessário.
3. Valide o site localmente e inclua capturas de tela quando houver mudanças visuais.
4. Abra uma pull request descrevendo o que mudou.

O GitHub Actions valida as pull requests. Pushes em `master` ou `main` publicam automaticamente o site no GitHub Pages usando as dependências do `uv.lock`.
