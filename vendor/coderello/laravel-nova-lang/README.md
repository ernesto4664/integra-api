<p align="center"><img alt="Laravel Nova Lang" src="https://coderello.com/images/packages/laravel-nova-lang.png" width="450"></p>

<p align="center">Language files for <b>Laravel Nova</b> translated into 40+ languages.</p>

This is not an official Laravel package, but is built from community contributions. If you are able to help by submitting a new language, reviewing an existing language, or adding missing keys, please read our [contributing guidelines](CONTRIBUTING.md) and raise a PR.

<hr>

## Installation

```bash
composer require coderello/laravel-nova-lang
```

## Usage
### Publish Command
* Publish translations for one language:
  ```bash
  php artisan nova-lang:publish de
  ```

* Publish translations for multiple languages (comma-separated):
  ```bash
  php artisan nova-lang:publish de,ru
  ```

* Publish translations for all available languages:
  ```bash
  php artisan nova-lang:publish --all
  ```

* Publish translations and override existing files:
  ```bash
  php artisan nova-lang:publish de,ru --force
  ```

#### Aliases
The language codes chosen for the files in this repository may not match the preferences for your project. You can use the `‑‑alias` option to publish locales using a different filename.

* Publish translations for one language with an alias, using the simple format `{alias}`:
  ```bash
  php artisan nova-lang:publish de --alias=de-DE
  ```
  This will publish the file `de-DE.json`.

* Publish translations for multiple languages with multiple aliases, using the format `{locale}:{alias}` (comma-separated):
  ```bash
  php artisan nova-lang:publish de,ru,fr --alias=de:de-DE,ru:ru-RU
  ```
  This will publish the files `de-DE.json`, `ru-RU.json` and `fr.json` (no alias).

* Aliases can also be used with the `--all` flag:

  ```bash
  php artisan nova-lang:publish --all --alias=es:es-ES
  ```
  You do not need to supply an alias for every locale that is to be published, only those that you wish to override.

* Here are some example aliases for common use cases:

  * Use Chinese with scripts instead of regions: `zh-CN:zh-Hans,zh-TW:zh-Hant`
  * Default to Brazilian Portuguese over European: `pt:pt-PT,pt-BR:pt`
  * Default to Serbian in Latin script over Cyrillic: `sr-Latn:sr,sr:sr-Cyrl`


* There is also an `‑‑underscore` or `‑U` switch to publish locales with an underscore separator instead of a hyphen. This can be used in combination with aliases.

### Development Commands (debug mode only)

You must have the `app.debug` config option set to true for these commands to be available:

#### Missing Command

This command is to assist contributors to find any untranslated keys for their chosen language.

A stub JSON file will be created at `storage_path('app/nova-lang/missing/{locale}.json')`. You can copy those keys into the `resources/lang/{locale}.json` language file in your own fork of the repository, translate them and create a pull request.

* Output missing translation keys for one or more languages:
```bash
php artisan nova-lang:missing de,ru
```

* Output missing translation keys for all languages:
```bash
php artisan nova-lang:missing --all
```

#### Reorder Command

This command is to assist contributors to ensure that the translation keys for their chosen language are in the same order as the `en.json` source file from Laravel Nova.

If you have imported the keys you are translating into a translation string management tool, the original order of the keys may be lost when you reexport the file. This makes the diff difficult to read because it will highlight all keys rather than just those which you have added or updated.

A new JSON file will be created at `storage_path('app/nova-lang/reorder/{locale}.json')`. You can copy the contents of this file to `resources/lang/{locale}.json` in your fork before you raise a PR.

* Output reordered translation keys for one or more languages:
```bash
php artisan nova-lang:reorder de,ru
```

* Output reordered translation keys for all languages:
```bash
php artisan nova-lang:reorder --all
```

#### Country Names Command

This command is to assist contributors to download the country names automatically from the [Unicode Common Locale Data Repository](http://cldr.unicode.org/translation/displaynames/country-names) (CLDR). We use the CLDR as the definitive source for country names, as described in the contribution guidelines.

A new JSON file will be created at `storage_path('app/nova-lang/countries/{locale}.json')`. You can merge the keys from this file into `resources/lang/{locale}.json` in your fork before you raise a PR.

* Output country names for one or more languages:
```bash
php artisan nova-lang:country de,ru
```

* Output country names for all languages:
```bash
php artisan nova-lang:country --all
```

#### Stats Command

This command is to assist maintainers to update the completeness of each language and list of contributors in this README file.

A `README.excerpt.md` and `contributors.json` file will be created at `storage_path('app/nova-lang')`. You can copy those files into your own fork of the repository and create a pull request.

* Output list of languages, lines translated and contributors:
```bash
php artisan nova-lang:stats
```

Ensure you have created a GitHub personal access token and saved it as a `GITHUB_TOKEN_NOVALANG` env variable in your master Laravel application in order to download the most recent contributions.

## Available Languages

Note: There is no need to update the count of translated strings and add your username below, as this is done by script when your PR is merged.

Total languages ![42](https://img.shields.io/badge/42-gray?style=flat-square)  
Total lines translated ![16,209 (94.6%)](https://img.shields.io/badge/16,209-94%25-yellow?style=flat-square)

| Code | Language | Translated files | Lines translated | Thanks to |
| --- | --- | --- | --- | --- |
| `en` | English | [`php`](resources/lang/en) [`json`](resources/lang/en.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [taylorotwell](https://github.com/taylorotwell), [bonzai](https://github.com/bonzai), [davidhemphill](https://github.com/davidhemphill), [jbrooksuk](https://github.com/jbrooksuk), [themsaid](https://github.com/themsaid), [kitbs](https://github.com/kitbs), [dillingham](https://github.com/dillingham) |
| `ar` | Arabic | [`php`](resources/lang/ar) [`json`](resources/lang/ar.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [saleem-hadad](https://github.com/saleem-hadad), [danyelkeddah](https://github.com/danyelkeddah), [omarfathy13](https://github.com/omarfathy13), [CaddyDz](https://github.com/CaddyDz), [i3asm](https://github.com/i3asm), [Arryan](https://github.com/Arryan) |
| `cs` | Czech | [`php`](resources/lang/cs) [`json`](resources/lang/cs.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [walaskir](https://github.com/walaskir), [theimerj](https://github.com/theimerj), [genesiscz](https://github.com/genesiscz), [walaski](https://github.com/walaski) |
| `nl` | Dutch | [`php`](resources/lang/nl) [`json`](resources/lang/nl.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [DannyvdSluijs](https://github.com/DannyvdSluijs), [happyDemon](https://github.com/happyDemon), [steefmin](https://github.com/steefmin), [jschram](https://github.com/jschram), [sebastiaanspeck](https://github.com/sebastiaanspeck), [preliot](https://github.com/preliot), [webovatenl](https://github.com/webovatenl), [daniel-de-wit](https://github.com/daniel-de-wit) |
| `fr` | French | [`php`](resources/lang/fr) [`json`](resources/lang/fr.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [MarceauKa](https://github.com/MarceauKa), [Yannik-Slym](https://github.com/Yannik-Slym), [InfinityWebMe](https://github.com/InfinityWebMe), [kitbs](https://github.com/kitbs), [shaffe-fr](https://github.com/shaffe-fr), [Arryan](https://github.com/Arryan), [voidgraphics](https://github.com/voidgraphics), [KillianH](https://github.com/KillianH) |
| `de` | German | [`php`](resources/lang/de) [`json`](resources/lang/de.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [pille1842](https://github.com/pille1842), [shieraki](https://github.com/shieraki), [kitbs](https://github.com/kitbs), [tobiasthaden](https://github.com/tobiasthaden), [dakira](https://github.com/dakira) |
| `hu` | Hungarian | [`php`](resources/lang/hu) [`json`](resources/lang/hu.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [milli05](https://github.com/milli05), [bgeree](https://github.com/bgeree), [lintaba](https://github.com/lintaba) |
| `id` | Indonesian | [`php`](resources/lang/id) [`json`](resources/lang/id.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [dvlwj](https://github.com/dvlwj), [opanegro](https://github.com/opanegro) |
| `es` | Spanish | [`php`](resources/lang/es) [`json`](resources/lang/es.json) | ![408 (100%)](https://img.shields.io/badge/408-100%25-brightgreen?style=flat-square) | [kitbs](https://github.com/kitbs), [joebordes](https://github.com/joebordes), [ajmariduena](https://github.com/ajmariduena), [iksaku](https://github.com/iksaku), [IGedeon](https://github.com/IGedeon), [Arryan](https://github.com/Arryan), [kennyhorna](https://github.com/kennyhorna), [miktown](https://github.com/miktown), [xcodinas](https://github.com/xcodinas), [dgtal](https://github.com/dgtal), [rodrigore](https://github.com/rodrigore) |
| `it` | Italian | [`php`](resources/lang/it) [`json`](resources/lang/it.json) | ![407 (99.8%)](https://img.shields.io/badge/407-99%25-green?style=flat-square) | (unknown), [alfonsocuccaro](https://github.com/alfonsocuccaro), [manuelcoppotelli](https://github.com/manuelcoppotelli), [dejdav](https://github.com/dejdav) |
| `ru` | Russian | [`php`](resources/lang/ru) [`json`](resources/lang/ru.json) | ![407 (99.8%)](https://img.shields.io/badge/407-99%25-green?style=flat-square) | [hivokas](https://github.com/hivokas), [sanasol](https://github.com/sanasol), [den1n](https://github.com/den1n), [deadem](https://github.com/deadem), [soulshockers](https://github.com/soulshockers), [estim](https://github.com/estim) |
| `pt‑BR` | Brazilian Portuguese | [`php`](resources/lang/pt-BR) [`json`](resources/lang/pt-BR.json) | ![406 (99.5%)](https://img.shields.io/badge/406-99%25-green?style=flat-square) | [henryavila](https://github.com/henryavila), [pedrofurtado](https://github.com/pedrofurtado), [eduardokum](https://github.com/eduardokum), [saulo-silva](https://github.com/saulo-silva), [chbbc](https://github.com/chbbc), [IgorDePaula](https://github.com/IgorDePaula), [emtudo](https://github.com/emtudo) |
| `ca` | Catalan | [`php`](resources/lang/ca) [`json`](resources/lang/ca.json) | ![406 (99.5%)](https://img.shields.io/badge/406-99%25-green?style=flat-square) | [joebordes](https://github.com/joebordes), [gerardnll](https://github.com/gerardnll) |
| `nb` | Norwegian Bokmål | [`php`](resources/lang/nb) [`json`](resources/lang/nb.json) | ![405 (99.3%)](https://img.shields.io/badge/405-99%25-green?style=flat-square) | [einar-johan](https://github.com/einar-johan) |
| `ro` | Romanian | [`php`](resources/lang/ro) [`json`](resources/lang/ro.json) | ![405 (99.3%)](https://img.shields.io/badge/405-99%25-green?style=flat-square) | [BTeodorWork](https://github.com/BTeodorWork), [dtix](https://github.com/dtix), [alexgiuvara](https://github.com/alexgiuvara) |
| `sv` | Swedish | [`php`](resources/lang/sv) [`json`](resources/lang/sv.json) | ![405 (99.3%)](https://img.shields.io/badge/405-99%25-green?style=flat-square) | [tanjemark](https://github.com/tanjemark), [slackernrrd](https://github.com/slackernrrd) |
| `tr` | Turkish | [`php`](resources/lang/tr) [`json`](resources/lang/tr.json) | ![405 (99.3%)](https://img.shields.io/badge/405-99%25-green?style=flat-square) | [jnbn](https://github.com/jnbn), [bureken](https://github.com/bureken), [Milkhan](https://github.com/Milkhan), [sineld](https://github.com/sineld), [dilekuzulmez](https://github.com/dilekuzulmez) |
| `uk` | Ukrainian | [`php`](resources/lang/uk) [`json`](resources/lang/uk.json) | ![405 (99.3%)](https://img.shields.io/badge/405-99%25-green?style=flat-square) | [soulshockers](https://github.com/soulshockers), [Ostap34JS](https://github.com/Ostap34JS), [osbre](https://github.com/osbre) |
| `uz‑Latn` | Uzbek (Latin) | [`php`](resources/lang/uz-Latn) [`json`](resources/lang/uz-Latn.json) | ![405 (99.3%)](https://img.shields.io/badge/405-99%25-green?style=flat-square) | [shokhaa](https://github.com/shokhaa) |
| `af` | Afrikaans | [`php`](resources/lang/af) [`json`](resources/lang/af.json) | ![400 (98%)](https://img.shields.io/badge/400-98%25-green?style=flat-square) | [medlion](https://github.com/medlion) |
| `bs` | Bosnian | [`php`](resources/lang/bs) [`json`](resources/lang/bs.json) | ![400 (98%)](https://img.shields.io/badge/400-98%25-green?style=flat-square) | [hajro92](https://github.com/hajro92) |
| `ja` | Japanese | [`php`](resources/lang/ja) [`json`](resources/lang/ja.json) | ![400 (98%)](https://img.shields.io/badge/400-98%25-green?style=flat-square) | [Tsumagari](https://github.com/Tsumagari), [storyn26383](https://github.com/storyn26383) |
| `fa` | Farsi | [`php`](resources/lang/fa) [`json`](resources/lang/fa.json) | ![399 (97.8%)](https://img.shields.io/badge/399-97%25-green?style=flat-square) | [alirezamirsepassi](https://github.com/alirezamirsepassi), [mziraki](https://github.com/mziraki), [zareismail](https://github.com/zareismail) |
| `tk` | Turkmen | [`php`](resources/lang/tk) [`json`](resources/lang/tk.json) | ![399 (97.8%)](https://img.shields.io/badge/399-97%25-green?style=flat-square) | [kakajansh](https://github.com/kakajansh) |
| `pl` | Polish | [`php`](resources/lang/pl) [`json`](resources/lang/pl.json) | ![397 (97.3%)](https://img.shields.io/badge/397-97%25-green?style=flat-square) | [pzmarzly](https://github.com/pzmarzly), [Strus](https://github.com/Strus), [marekfilip](https://github.com/marekfilip), [mslepko](https://github.com/mslepko), [wiktor-k](https://github.com/wiktor-k) |
| `zh‑CN` | Chinese (Simplified) | [`php`](resources/lang/zh-CN) [`json`](resources/lang/zh-CN.json) | ![393 (96.3%)](https://img.shields.io/badge/393-96%25-green?style=flat-square) | [jcc](https://github.com/jcc), [zacksleo](https://github.com/zacksleo), [masterwto](https://github.com/masterwto) |
| `zh‑TW` | Chinese (Traditional) | [`php`](resources/lang/zh-TW) [`json`](resources/lang/zh-TW.json) | ![393 (96.3%)](https://img.shields.io/badge/393-96%25-green?style=flat-square) | [CasperLaiTW](https://github.com/CasperLaiTW), [zacksleo](https://github.com/zacksleo), [storyn26383](https://github.com/storyn26383) |
| `pt` | Portuguese | [`php`](resources/lang/pt) [`json`](resources/lang/pt.json) | ![377 (92.4%)](https://img.shields.io/badge/377-92%25-yellow?style=flat-square) | [Pedrocssg](https://github.com/Pedrocssg) |
| `da` | Danish | [`php`](resources/lang/da) [`json`](resources/lang/da.json) | ![356 (87.3%)](https://img.shields.io/badge/356-87%25-orange?style=flat-square) | [olivernybroe](https://github.com/olivernybroe), [rugaard](https://github.com/rugaard), [peterchrjoergensen](https://github.com/peterchrjoergensen) |
| `eu` | Basque | [`php`](resources/lang/eu) [`json`](resources/lang/eu.json) | ![354 (86.8%)](https://img.shields.io/badge/354-86%25-orange?style=flat-square) | [JonPaternain](https://github.com/JonPaternain) |
| `hr` | Croatian | [`php`](resources/lang/hr) [`json`](resources/lang/hr.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [defart](https://github.com/defart), [walaski](https://github.com/walaski) |
| `fil` | Filipino | [`php`](resources/lang/fil) [`json`](resources/lang/fil.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [granaderos](https://github.com/granaderos) |
| `fi` | Finnish | [`php`](resources/lang/fi) [`json`](resources/lang/fi.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [Krisseck](https://github.com/Krisseck) |
| `ka` | Georgian | [`php`](resources/lang/ka) [`json`](resources/lang/ka.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [akalongman](https://github.com/akalongman) |
| `hi` | Hindi | [`php`](resources/lang/hi) [`json`](resources/lang/hi.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [bantya](https://github.com/bantya) |
| `sr` | Serbian (Cyrillic) | [`php`](resources/lang/sr) [`json`](resources/lang/sr.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [marjanovicsteva](https://github.com/marjanovicsteva) |
| `sr‑Latn` | Serbian (Latin) | [`php`](resources/lang/sr-Latn) [`json`](resources/lang/sr-Latn.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [marjanovicsteva](https://github.com/marjanovicsteva) |
| `sk` | Slovak | [`php`](resources/lang/sk) [`json`](resources/lang/sk.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [hejty](https://github.com/hejty) |
| `sl` | Slovenian | [`php`](resources/lang/sl) [`json`](resources/lang/sl.json) | ![352 (86.3%)](https://img.shields.io/badge/352-86%25-orange?style=flat-square) | [morpheus7CS](https://github.com/morpheus7CS) |
| `lt` | Lithuanian | [`php`](resources/lang/lt) [`json`](resources/lang/lt.json) | ![351 (86%)](https://img.shields.io/badge/351-86%25-orange?style=flat-square) | [minved](https://github.com/minved) |
| `bg` | Bulgarian | [`php`](resources/lang/bg) [`json`](resources/lang/bg.json) | ![349 (85.5%)](https://img.shields.io/badge/349-85%25-orange?style=flat-square) | [BKirev](https://github.com/BKirev) |
| `tl` | Tagalog | [`php`](resources/lang/tl) [`json`](resources/lang/tl.json) | ![345 (84.6%)](https://img.shields.io/badge/345-84%25-red?style=flat-square) | [rcjavier](https://github.com/rcjavier) |

## Missing Languages

The following languages are supported for the main Laravel framework by the excellent [caouecs/laravel-lang](https://github.com/caouecs/Laravel-lang) package. We would love for our package to make these languages available for Nova as well. If you are able to contribute to any of these or other languages, please read our [contributing guidelines](CONTRIBUTING.md) and raise a PR.

Parity with `caouecs/laravel-lang` ![40/75 (53.3%)](https://img.shields.io/badge/40%2F75-53%25-red?style=flat-square)

| Code | Language | Lines translated |
| --- | --- | --- |
| `sq` | Albanian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `az` | Azerbaijani | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `bn` | Bangla | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `be` | Belarusian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `zh‑HK` | Chinese (Hong Kong) | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `et` | Estonian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `gl` | Galician | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `de‑CH` | German (Switzerland) | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `el` | Greek | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `hy` | Armenian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `he` | Hebrew | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `is` | Icelandic | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `kn` | Kannada | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `kk` | Kazakh | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `km` | Khmer | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `ko` | Korean | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `lv` | Latvian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `mk` | Macedonian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `ms` | Malay | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `mr` | Marathi | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `mn` | Mongolian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `cnr` | Montenegrin | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `ne` | Nepali | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `nn` | Norwegian Nynorsk | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `ps` | Pashto | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `sc` | Sardinian | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `si` | Sinhala | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `sw` | Swahili | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `tg` | Tajik | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `th` | Thai | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `ur` | Urdu | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `ug` | Uyghur | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `uz‑Cyrl` | Uzbek (Cyrillic) | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `vi` | Vietnamese | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |
| `cy` | Welsh | ![0 (0%)](https://img.shields.io/badge/0-0%25-lightgray?style=flat-square) |