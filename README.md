# Datenbank-Test

## Initialisieren

- docker installieren (inkl. docker-compose)
- Container hochfahren

````shell
docker-compose up -d
````

- changesets ausführen

```shell
./liquibase update
```

## Testaufgabe
Verbindung mit der Datenbank herstellen:
psql -h localhost -d docker -U docker
Das Passwort ist postgres

Ausgangssituation:
Von unseren Partnern Hinz und Kunz haben wir Daten erhalten, die wir in unsere Datenbank einspielen sollen.
Die beiden arbeiten mit unterschiedlichen Systemen und geben uns die Daten deshalb in verschiedenen Formaten.
Wir haben die Daten erst einmal so, wie wir sie erhalten, in Importtabellen übertragen.

Aufgaben:

1. Erstelle eine sinnvolle Tabellenstruktur für die Daten. Wir bekommen die Daten zwar von verschiedenen Partnern, aber wir wollen keine getrennten Kundentabellen o. ä. haben. Wenn ein Kunde oder Vermittler von Hinz zu Kunz wechselt, wollen wir möglichst wenig Aufwand haben, um die Änderung bei uns einzutragen.

Erstelle hierfür ein Changelog für Liquibase. Die bisherigen Dateien für Liquibase findest du im Ordner "db".

2. Für die Ermittlung von Provisionen müssen wir wissen, wieviel Geld jeder Vermittler verwaltet. Erstelle hierfür ein oder mehrere Abfragen, die folgende Fragen beantworten:
   - Wieviel Vermögen haben die Kunden jedes einzelnen Vermittlers?
   - Einige Vermittler betreuen nicht nur Kunden sondern auch andere Vermittler. Wieviel Vermögen betreuen diese Vermittler insgesamt, also inklusive der Vermögen ihrer Untervermittler?
   - Wie groß ist der Anteil des betreuten Vermögens für die einzelnen Vermittler in Bezug auf ihr Unternehmen und in Bezug auf den Gesamtbestand in der Datenbank?
   
### Review

- PR mit Änderungen erstellen in dieses Repo
