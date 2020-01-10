# os-zaverecna-prace


# Závěrečná písemná práce z 3. ročníku

**Skupina: A**

## Popis

Jedná se o váš první den v práci. Aby si váš šéf vyzkoušel vaše dovednosti, rozhodl se vám dát cvičný úkol, který si za 45 minut přijde zkontrolovat.

## Zadání

- V systému vytvořte na druhém disku (sdx nebo vdx) **diskový oddíl o velikosti 500MB, na kterém vytvoříte LVM skupinu:** `zlab`.
- **Ve skupině zlab budou dva logické oddíly:**
    - první logický oddíl se jménem `home` o velikosti  **300MB**
    - druhý logický oddíl se jménem `swap` o velikosti **100MB**
- Logický oddíl se jménem `home` naformátujte filesystémem ext4 a zařiďte, aby se při spuštění systému mountoval na mounting point `/home`
- Logický oddíl se jménem `swap` naformátujte jako swap a zařiďte, aby se při spuštění systému aktivoval
- **V systému vytvořte uživatele:** franta, pepa, jarda, kde
    - každý z uživatelů má domovský adresář ve složce `/home`
    - každý z uživatelů má v domovském adresáři složky: Dokumenty, Stazene, Hudba, Videa
    - každý z uživatelů má jako login shell nastavený `/bin/bash`
    - uživatel **jarda** má sudo oprávnění, že může zastupovat kohokoliv a nemusí zadávat heslo
    - uživatel **pepa** a **franta** jsou v sekundární skupině kolegove
- Po vytvoření uživatelů a domovských adresářů, zarchivujte složku `/home` s gzip kompresí. Archiv pojmenujte `back1.gz` a uložte ho do složky `/backups`.
- Na logickým oddíle se jménem `home` nastavte **kvótování tak, že:**
    - **ani jeden z našich vytvořených uživatelů** nepřesáhne skupinovou kvótu 70% zaplnění, kde je to při 65% upozorní
    - **franta** může obsadit až 100MB a při 70MB ho to upozorní
    - **pepa** může obsadit až 150MB, ale při 70MB též dostane upozornění
    - **jarda** si může dělat co chce a nikdy upozornění nedostane (co se týká uživatelské kvóty)
- Napište skript dán absolutní cestou `/time.sh`, který každou minutu vypíše pozdrav a datum s aktuálním časem. Skript spusťte jako daemona.

**Ukázka výpisu:**

```bash
Dobrý den, dnes je 5.1.2020, 13:05.
```
