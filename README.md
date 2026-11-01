# claude-project-template

Заготовка нового проекта под Claude Code. Своей логики здесь нет: wiki flow по Karpathy, оркестрация Opus → Sonnet/Haiku, имена сессий, уведомления и git-защита приходят из плагина [claude-setup](https://github.com/joerude/claude-setup). Шаблон поэтому не устаревает: улучшения плагина доходят до всех проектов сами.

## Как начать проект

1. **Use this template** → **Create a new repository**, или:

   ```bash
   gh repo create my-project --private --template joerude/claude-project-template --clone
   ```

2. Откройте папку в Claude Code и доверьте её. Claude Code увидит в `.claude/settings.json` marketplace `claude-setup` и предложит поставить плагин — согласитесь.
3. Выполните `/claude-setup:setup`. Он спросит, какие части нужны (wiki, оркестрация, имена сессий, git-политика), допишет блоки в `CLAUDE.md` и создаст `index.md`, `log.md`, `BACKLOG.md`, `input/`.
4. Заполните `{{...}}` в шапке `CLAUDE.md` (стек, команды, соглашения) и удалите этот README или замените своим.

## Что внутри

| Файл | Зачем |
| --- | --- |
| `.claude/settings.json` | объявляет marketplace `joerude/claude-setup` и включает плагин для проекта |
| `CLAUDE.md` | шапка проекта; блоки `claude-setup:*` дописывает `/claude-setup:setup` |
| `.gitignore` | личные `settings.local.json` и `CLAUDE.local.md` не попадают в git |

Существующий проект подключается без шаблона: поставьте плагин и выполните `/claude-setup:setup` — он сам добавит эти настройки.

Репозиторий плагина приватный: на новой машине сначала `gh auth login`.
