Git komandos
============

_Čia yra pateikiamas pagrindinių (dažniausiai naudojamų) Git komandų sąrašas ir jų paaiškinimai._

Norintiems plačiau susipažinti su Git galimybės, rekomenduočiau susipažinti su [Atlassian parengta Git mokymo medžiaga](https://www.atlassian.com/git/tutorials), o taip pat žvilgtelėkite [naudingų nuorodų](#naudingos-nuorodos) skyrių.

Kad būtų paprasčiau suprasti Git komandas, reikia pirma susipažinti kokias būsenas failas gali įgyti Git'o akimis: ![Galimos failų būsenos](https://image.slidesharecdn.com/gittutorial-150724014321-lva1-app6891/95/git-tutorial-8-638.jpg?cb=1437702443)

### Git atsisiuntimas ir konfigūravimas

Git atsisiuntimas (visoms operacinėms systemoms): [http://git-scm.com](http://git-scm.com)

| Git komanda | Paaiškinimas |
| ----------- | ------------ |
| `git config --global user.name "Vardas Pavardė"`           | Nustatykite autoriaus (Git naudodojo) vardą     |
| `git config --global user.email vardas.pavarde@mif.vu.lt`  | Nustatykite autoriaus (Git naudodojo) el. paštą |
| `git config --list`  | Patikrinti vartotojo profilį |

### Naujo projekto kūrimas ir klonavimas (atsisiuntimas) 

| Git komanda | Paaiškinimas |
| ----------- | ------------ |
| `git init`  | Inicializuoti lokalią Git repoziciją (saugyklą) dabartiniame kataloge |
| `git clone <url-adresas>` | Sukurti lokalią kopiją nuotolinės repozicijos           |

### Bazinės Git komandos

| Git komanda | Paaiškinimas |
| ----------- | ------------ |
| `git status` | Patikrinti repozicijos statusą |
| `git add <failo-vardas>` | Pridėti (angl. stage) naują/modifikuotą failą (į index sritį) kitam commit'ui |
| `git add -A` | Pridėti (stage) visus naujus ir modifikuotus vailus į index sritį |
| `git commit`  | Commit'inti išsaugotus (stage'intus) failus (index srityje) |
| `git commit -m "Commit žinutė"` | Commit'inti išsaugotus (stage'intus) failus (index srityje) neatveriant Vim ar kito redaktoriaus commit'o žinutės rašymui |
| `git commit -a` | dvi komandos: `git commit + git add` vienoje |
| `git rm -r <failo-vardas>` | Ištrinti failą/katalogą iš Git repozicijos |
| `git log` | Parodyti repozicijos commit'ų istoriją naudojant standartinį formatą |
| `git log --summary` | Parodyti išsamią repozicijos commit'ų istoriją |t
| `git diff` | Parodyti unstaged skirtumus tarp index srities ir darbinio katalogo |

### Dalintis ir atnaujinti (Git) projektus su nuotoliniais serveriais ([GitHub](http://www.github.com/), [GitLab](http://www.gitlab.com/), [Bitbucket](https://bitbucket.org/) ir pan.)

| Git komanda | Paaiškinimas |
| ----------- | ------------ |
| `git remote add <alias'as> <serverio-adresas>` | Pridėti nuotolinę repoziciją, prieš siunčiant (push'inant) į ją commit'us (origin yra numatytasis vardas alias'ui) |
| `git remote -v` | Parodykite visas šiuo metu sukonfigūruotas nuotolines repozicijas |
| `git push origin <branch-vardas>` | Siūsti branch'ą į nuotolinę repoziciją |
| `git push -u origin <branch-vardas>` | Siūsti branch'ą į nuotolinę repoziciją ir įsiminti dabartinį branch'ą (master yra default vardas) |
| `git push` | Siūsti atnaujinimus į nuotolinę repoziciją serveryje (į įsimintą branch'ą) |
| `git push origin --delete <branch-vardas>` | Ištrinti branch'ą nuotoliniame serveryje |
| `git pull` | Atnaujinti lokalią repozicją pagal nuotolinę versiją (atsisiūsti commit'us iš serverio) |

### Šakojimas (angl. branch) & ir suliejimas (angl. merge)

| Command | Description |
| ------- | ----------- |
| `git branch` | Parodyti visus branch'us (žvaigždutė pažymi šiuo metu aktyvų) |
| `git branch -a` | arodyti visus (lokalius ir nuotolinius) branch'us |
| `git branch <branch-vardas>` | Sukurti naują branch'ą |
| `git branch -d <branch-vardas>` | Ištrinti branch'ą |
| `git push origin --delete <branch-vardas>` | Ištrinti nuotolinį branch'ą (serveryje) |
| `git checkout -b <branch-vardas>` | Sukurti naują branch'ą ir persijungti į jį |
| `git checkout -b <branch-vardas> origin/<branch-vardas>` | Klonuoti nuotolinį branch'ą ir persijungti į jį |
| `git checkout <branch-vardas>` | Persijungti iš vieno branch'o į kitą branch'ą |
| `git checkout -- <failo-vardas>` | Išmesti (panaikinti) failo pakeitimus |
| `git merge [<branch-vardas>` | Sulieti (merge) branch'ą į šiuo metu aktyvų branch'ą |

### Git repozicijos inicializavimas ir paruošimas push'inimui į Github'ą naudojantis Git Bash terminalu

1. Kataloge talpinančiame Jūsų **Codeblock** projektą įvykdykite: `git init`
2. Sukuriame `.gitignore` failą įvykdę komandą: `touch .gitignore`
3. Atsidarote `.gitignore` failą su Jūsų mėgstamu redaktoriumi (nebūtina naudoti Vim :) ) ir pridedate tokias eilutes:

```
obj/
bin/
*.cbp
*.layout
```
kuriomis pasakome, kad mes nenorime, kad Git'as sektų šiuos katalogus/failus.

4. Įvykdome `git add .`
5. Įvykdome `git commit -m "Komito zinute"`
6. Tuomet einate į GitHub ir susikuriate naują repoziciją, pvz. `Darbas1` į kurią norėsite push'inti
7. Tuomet Git Bash'e įvykdote `git remote add origin <jusu-github-repozicijos-adresas>`
8. Galiausiai viską nusiunčiame į GitHub serverį: `git push origin master

## Naudingos nuorodos

1. [Github - Git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)
2. [Atlassian - Git cheat sheet](https://www.atlassian.com/dam/jcr:8132028b-024f-4b6b-953e-e68fcce0c5fa/atlassian-git-cheatsheet.pdf)
3. [Adding an existing project to GitHub using the command line](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)
4. [Adding an existing project to GitHub using GitHub Desktop](https://help.github.com/desktop/guides/contributing-to-projects/adding-an-existing-project-to-github-using-github-desktop/)

