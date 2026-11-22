# Keep Settings in `.echoes`

> A runite's own settings — a URL, a token, a choice the user made — live in its echoes, through `Keeper::item()`. Rune has no `.env`, and does not need one.

**Runes:** Keeper · **From:** Act 1

```php
// php cast config --set=api --value=https://example.test | php cast config | php cast ping
Chanter::cast('config --set --value', function() {
  $config = Keeper::item('config') ?: new stdClass;         // .echoes/<runite>/config.json
  $key = Chanter::spell('set');
  if (is_string($key)) {
    $config->$key = (string) Chanter::spell('value');
    Keeper::item('config', $config);
    Whisper::echo("Saved $key{{nl}}");
  }
  foreach ($config as $name => $value) {
    Whisper::echo("$name = $value{{nl}}");
  }
}, 'Read or set a setting. --set=name --value=...');

Chanter::cast('ping', function() {
  $config = Keeper::item('config');
  Whisper::echo('calling ' . ($config->api ?? '(no api set: php cast config --set=api --value=...)') . '{{nl}}');
}, 'Use a setting.');
```

## How it works
- `Keeper::item('config', $data)` writes `.echoes/<runite>/config.json`; `Keeper::item('config')` reads it back as an object (or `null`). It is a plain JSON file — open it, edit it by hand, or let a cast write it.
- `.echoes/` does the work a `.env` file does elsewhere: it sits **next to the runite**, holds what belongs to this machine and this runite only, and stays **out of git** — `php cast sentinel --gitignore` hides every `.echoes/` (and `vendor/`).
- Each runite has its own folder (`.echoes/cast/`, `.echoes/ember/`…), so two runites in one folder never read each other's settings.
- Settings **do not travel**: items are never shards, so a relic does not carry them. Whoever opens the relic sets their own — say so in a cast like `config` above.
- Keeper must be engraved with its flow: `Keeper::begin()` / `Keeper::end()`. Without them `Keeper::item()` saves nothing ([Keeper](../acts/1-first-resonance/keeper.md)).

## Why not `.env`
Rune does not handle the environment: no rune reads `.env`, and none is planned. A runite that needs a value per machine keeps it in its echoes, as above. A value that must come from the shell (a CI secret, a container variable) is read with PHP's own `getenv()`, inside the cast that needs it.

## Not a vault
The JSON is plain text. For a value that should not be read at a glance, seal it first: [Seal a Secret](secrets.md) — a lore seal, not encryption.
