# Liberation

> The Liberation of Forte — your app is no longer bound to the PHP of the machine it lands on.

*Forte* is freedom in ability. A runite needs PHP to run; Liberation lets the project keep its own PHP runtime next to it, so the app runs the same wherever it goes.

→ Reference: [Modes](../../../reference/modes.md#liberation--your-own-php-runtime) · [Sentinel](../../../reference/runites/sentinel.md)

## Unlock it
```bash
php cast sentinel --liberation
```
```
::S E N T I N E L
[√] The Liberation of Forte is unlocked: Rune\Ethereal::liberation();
[i] Read @liberation/README.md
```
The entrance now reads *The Liberation of Forte* — the highest caption of all modes.

## Take a runtime
```bash
php cast sentinel --runtime-install
```
```
SENTINEL :: Runtime Install
[i] php@8.3.6 for linux x86_64: https://dl.static-php.dev/static-php-cli/common/php-8.3.6-cli-linux-x86_64.tar.gz
[√] Runtime kept: @liberation/php@8.3.6/
[i] Run with it: @liberation/php@8.3.6/php cast
```
- Without a value it takes the PHP you are running now. Ask for another: `--runtime-install=php@8.3`.
- Take one for another system: `--os=windows|linux|macos`, `--arch=x86_64|aarch64` — a Linux machine can prepare the runtime of a Windows app.
- **Windows** builds come from windows.php.net (`php@8.3` is enough: the newest 8.3, checked by its sha256). Rune writes a small `php.ini` with `extension_dir = "ext"` and the extensions it reaches for.
- **Linux and macOS** builds are static PHP from static-php; give the full version (`php@8.3.14`) unless it is the PHP you are running.

```
@liberation/
├── php@8.3.36/        php.exe, ext/, php.ini
├── liberation.json    the runtime in use
└── README.md
```

## Run with it
```bash
@liberation/php@8.3.36/php.exe cast          # Windows
@liberation/php@8.3.6/php cast               # Linux, macOS
```

## Keep it tidy
```bash
php cast sentinel --runtime-list             # every runtime, and the one in use
php cast sentinel --runtime-remove=php@8.3.36
```

## Notes
- PHP needs `curl` or `allow_url_fopen` (and openssl for `https`) to download, and the `phar` extension to open the archive.
- A runtime is large (tens of MB). Whether `@liberation/php@*/` goes into git is your choice — `liberation.json` alone tells another machine which PHP the app expects.
- Liberation can be open together with [Evolution](../3-evolution-of-eidos/evolution.md) and [Federation](reliquary.md).
