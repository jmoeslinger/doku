---
icon: git-branch
---
# Arbeit mit Git

## Konfiguration

Die Kofiguration wird bei der ersten Verwendung durchgeführt.
Anschließend gelten die Werte für alle neuen Projekte

In der Eingabeaufforderung werden folgende Befehlen ausgeführt:

```
git config --global user.name "Jakub Möslinger"
git config --global user.email "jmoeslinger@schueler.hakzell.at"
git config --global init.defaultBranch "main"
```

Da der Parameter `--global` verwendet wird,
können diese Befehle in einem neliebigen Verzeichnis ausgeführt werden

>**Hinweis:** Falls Git neu installiert wurde,
müssen sämtliche Eingabeaufforderungen (Fenster) vor der Befehlsausführung geschlossen werden.

Nach der Ausführung dieser Befehle befindet sich im Benutzerprofil (im Explorer `userrprofile`) eine datei names `.gitconfig` mit folgendem Inhalt:

[user]
	name = Jakub Möslinger
	email = jmoeslinger@schueler.hakzell.at
[init]
	defaultBranch = main

![Benutzerprofil](assets/userprofile.png)

![config-Datei](assets/git-configdatei.png)

## Allgemeines

