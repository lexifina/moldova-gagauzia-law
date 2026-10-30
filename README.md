# Gagauzia (Gagauz Yeri): law in git

The laws of the Autonomous Territorial Unit of Gagauzia (Gagauz Yeri), in the Republic of Moldova, in git: one file per article, as the People's Assembly of Gagauzia (Halk Topluşu) publishes them. `git blame`, `git log` and `tools/on.py` work as in the other repositories of the shared design.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `md-ga/`. The national law is in [lexifina/moldova-law](https://github.com/lexifina/moldova-law).

The text is in Russian, the language the Assembly publishes its laws in.

## What this repository holds

- `ulozhenie/`: the Уложение Гагаузии (Gagauz Yeri), the basic law of Gagauzia (Law No. 28-XXX/I of 14 May 1998), in the text as amended to 5 March 2020, as the Assembly publishes it ("Изменено на 05.03.2020 года"). It is the oldest version available: the earlier texts and the amending laws are not named in it.
- `zakon-<number>/`: each law the Assembly lists on its page "Законы АТО Гагаузия (Гагауз-Ери)", as adopted, or as amended where the post says "Изменено на" / "Изменен по состоянию на". Amending laws are recorded as laws of their own; they are not applied to the laws they amend.

Left out: the Law of the Republic of Moldova No. 344-XIII on the special legal status of Gagauzia (national law, listed on the same page); posts that give the text only in an embedded Google Drive viewer; posts with no adoption date in their closing lines or title; a second post of the same law; six laws whose articles cannot be told apart (quoted articles, or numbers that repeat).

## Source

Народное Собрание Гагаузии (Halk Topluşu), <https://halktoplushu.md>: the page
<https://halktoplushu.md/normativnaya-baza/zakony-ato-gagauziya-gagauz-eri> and each law's post (`/archives/<id>`).

## Dates

Each law has one commit, dated at noon, Europe/Chisinau, on the day the People's Assembly adopted it (from its title and its closing line, "мун. Комрат, <date>"). The day a law took effect, on its publication in the official bulletin, is not given by the source; where the law's own text has an entry-into-force clause, the commit quotes it. A text marked "Изменено на <date>" is dated that day and labelled as the oldest version available.

## Files

`st-007.md` is Статья 7 (Roman-numbered articles of amending laws, Статья I, II, are `st-001`, `st-002`); `preambula.md` is the text before the first article (title, number, date, enacting formula); `soderzhanie.md` a table of contents where the law has one; `tekst.md` the body of a law written without articles; `podpis.md` the signature, place, date and number. Chapter and section headings are `##` lines at the top of the next article. One paragraph, list item or table row per line (table cells joined by " | ").

## How it is checked

- Every law is read back from git on the day of its version and the day before (`tools/check_repo.py`); both must match the corpus.
- The letters and digits of every law, file by file in order, equal those of the Assembly's page, read a second time with a separate reader (every tag stripped by a regular expression, not the HTML parser the build uses).

## Limits

This is not an official publication. Most laws are recorded as adopted: later amendments are separate laws here, not applied to the text. Check the official bulletin of Gagauzia before relying on any text.
