# claude-project-template

Заготовка нового проекта под Claude Code. Своей логики здесь нет: wiki flow по Karpathy, оркестрация Fable → Opus/Sonnet/Haiku, имена сессий, уведомления и git-защита приходят из плагина [claude-setup](https://github.com/joerude/claude-setup). Шаблон поэтому не устаревает: улучшения плагина доходят до всех проектов сами.

Вторым плагином подключён [unslop](https://github.com/heydamir/unslop) (Damir Sokolovsky, CC BY 4.0): `/unslop` или просьба «почисти этот экран» превращает навайбкоженный UI с фиолетовыми градиентами, свечением и эмодзи в продуманный интерфейс. Сначала аудит и направление, правки — только после вашего ответа.

## Как начать проект

1. **Use this template** → **Create a new repository**, или:

   ```bash
   gh repo create my-project --private --template joerude/claude-project-template --clone
   ```

2. Откройте папку в Claude Code и доверьте её. Claude Code увидит в `.claude/settings.json` marketplace `claude-setup` и `heydamir` и предложит поставить плагины — согласитесь.
3. Выполните `/claude-setup:setup`. Он спросит, какие части нужны (wiki, оркестрация, имена сессий, git-политика), допишет блоки в `CLAUDE.md` и создаст `index.md`, `log.md`, `BACKLOG.md`, `input/`.
4. Заполните `{{...}}` в шапке `CLAUDE.md` (стек, команды, соглашения) и удалите этот README или замените своим.

## Что внутри

| Файл | Зачем |
| --- | --- |
| `.claude/settings.json` | объявляет marketplace `joerude/claude-setup` и `heydamir/unslop` и включает оба плагина для проекта |
| `CLAUDE.md` | шапка проекта; блоки `claude-setup:*` дописывает `/claude-setup:setup` |
| `.gitignore` | личные `settings.local.json` и `CLAUDE.local.md` не попадают в git |

Существующий проект подключается без шаблона: поставьте плагин и выполните `/claude-setup:setup` — он сам добавит настройки claude-setup. unslop в существующий проект ставится отдельно:

```bash
claude plugin marketplace add heydamir/unslop
claude plugin install unslop@heydamir --scope project
```

Снимок живого сайта и story-видео unslop требуют Playwright (`npm install -D playwright && npx playwright install chromium`) и ffmpeg; для обычной чистки экрана они не нужны. Не нужен unslop в проекте без UI — `.claude/settings.local.json` → `enabledPlugins: {"unslop@heydamir": false}`.

Репозиторий плагина приватный: на новой машине сначала `gh auth login`.
