# Änderungen machen (Making Changes)

## Ziele (Goals)
Um zu lernen, den Zustand des Arbeitsverzeichnisses zu überwachen.

(To learn how to monitor the state of the working directory.)

## 1. Ändern der „Hallo Welt!“-Seite (Modifying the “Hello World!” Page)
Fügen wir unserer Begrüßung einige HTML-Tags hinzu. Ändere den Dateiinhalt in:

(Let’s add some HTML tags to our greeting. Change the file content to:)

```html
<h1>Hello, World!</h1>
```

## 2. Überprüfen des Status (Checking the Status)
Überprüfe den Status des Arbeitsverzeichnisses.

(Check the status of the working directory.)

Befehl(Command):  
```bash
git status
```

Ergebnis(Result):  
```bash
$ git status
# On branch main
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working irectory)
#
#   modified:   hallo.html
#
# no changes added to commit (use "git add" and/or "git commit -a")
```

Der erste wichtige Aspekt hier ist, dass Git weiß, dass die hallo.html-Datei geändert wurde, aber diese Änderungen noch nicht in das Repository übernommen wurden.

(The first important point here is that Git knows the file hallo.html has been changed, but these changes have not yet been added to the repository.)

Ein weiterer Aspekt ist, dass die Statusmeldung Hinweise darauf gibt, was als nächstes zu tun ist. Wenn du diese Änderungen zum Repository hinzufügen möchtest, verwende den `git add` Befehl. Um die Änderungen rückgängig zu machen, verwende `git checkout`.

(Another important point is that the status message gives you hints about what to do next. If you want to add these changes to the repository, use the git add command. To undo the changes, use git checkout.)

## Level abschließen(Completing the Level)
Hast du alles richtig gemacht? Überprüfe es mit dem Befehl `npm start` innerhalb vom Git-Adventure Verzeichnis und schalte das nächste Level frei (docs/03-level.md).

(Did you do everything correctly? Check using the npm start command inside the Git Adventure directory and unlock the next level (docs/03-level.md).)