<!-- Filename: Smart_Search_on_large_sites / Display title: Intelligente Suche auf großen Websites -->

## Seitenindexierung

Die Smartsuche funktioniert, indem sie einen unabhängigen Index von Suchbegriffen in mehreren Datenbanktabellen erstellt und pflegt. Das Problem bei großen Websites ist, dass der Indexierungsprozess sehr ressourcenintensiv in Bezug auf CPU, Speicher und Festplattennutzung sein kann. Selbst nach der anfänglichen Erstellung des Indexes können auch inkrementelle Updates ressourcenintensiv sein. Die gute Nachricht ist, dass das Abfragen des Indexes eine relativ schnelle und ressourcenschonende Operation ist.

Die Smartsuche ist für die Mehrheit der Joomla-Seiten geeignet. Allerdings stellt die Suche besondere Herausforderungen für große Websites dar. Es sollte daran erinnert werden, dass die Smartsuche eine reine PHP-Implementierung einer Suchmaschine ist, und besonders große Websites sind möglicherweise besser bedient mit einer eigenständigen Suchmaschine wie Solr.

Um die Smartsuche auf einer großen Website zu nutzen, müssen Sie wahrscheinlich einige der Konfigurationseinstellungen anpassen. Im Folgenden finden Sie einige allgemeine Hinweise, worauf Sie achten sollten und was Sie versuchen können zu optimieren. Es gibt eine Reihe bekannter ungelöster Probleme im Hinblick auf die Nutzung der Smartsuche auf großen Websites, die hoffentlich in zukünftigen Versionen behoben werden, und diese werden hier ebenfalls beschrieben.

## Verwenden Sie immer den CLI-Indexer

Da der anfängliche Indexierungsprozess lange dauern kann, ist es am besten, den Indexer über die Kommandozeile auszuführen, um Probleme durch abgelaufene Browser-Sitzungen zu vermeiden. Der CLI-Indexer läuft nicht ab, egal wie lange er zur Fertigstellung benötigt, und kann leicht abgebrochen werden, wenn Probleme auftreten. Darüber hinaus sind Fehlermeldungen mit dem CLI-Indexer sichtbar, während sie beim Ausführen über den Administrator verborgen sind.

Um das CLI zu verwenden, öffnen Sie ein Terminal, wechseln Sie in den cli-Ordner im Stammverzeichnis Ihrer Website und geben Sie den folgenden Befehl ein:

```
php joomla.php finder:index
```

## Stapelverarbeitung

Der Indexer teilt den Indexierungsauftrag in Stapel von Inhaltsbeiträgen auf. Standardmäßig ist die Stapelgröße auf 30 eingestellt, was bedeutet, dass bis zu 30 Inhaltsbeiträge pro Stapel indexiert werden. Das Erhöhen der Stapelgröße kann den Indexierungsprozess potenziell beschleunigen, aber es wird mehr Speicher und möglicherweise mehr temporären Festplattenspeicher verwenden.

## Speicherprobleme

Wenn der Indexer nicht genug Speicher hat, versuchen Sie, die folgenden Anpassungen nacheinander auszuprobieren, bis das Problem behoben ist.

1.  Verringern Sie die Batch-Größe. Wenn Sie besonders große Inhalte haben, kann der Indexer auch bei einem einzelnen Inhaltsobjekt nicht genug Speicher haben, daher versuchen Sie zunächst, die Batch-Größe auf 5 zu reduzieren. Wenn immer noch ein Speicherproblem auftritt, verringern Sie sie auf 1.
2.  Wenn Sie dem Indexer mehr Speicher zuweisen können, tun Sie das. Sie können den dem Kommandozeilen-Indexer zugewiesenen Speicher durch einen zusätzlichen Parameter in der Kommandozeile erhöhen. Um beispielsweise das Speichertlimit auf 256 MB zu erhöhen, verwenden Sie den folgenden Befehl und ersetzen Sie die *256M* durch so viel Speicher, wie Sie sicher einem Prozess auf Ihrem System zuweisen können.<br>
    *php -d memory_limit=256M finder_indexer.php*
3.  Verringern Sie das Speichertabellen-Limit. Der Standardwert ist auf 30.000 Begriffe festgelegt, was bedeutet, dass sobald die temporäre In-Speicher-Tabelle *#__finder_tokens* diese Anzahl von Zeilen erreicht, der Indexer stattdessen eine Festplattentabelle verwendet. Es kann sein, dass Sie nicht genug Speicher haben, um eine volle oder fast volle Speichertabelle zu verarbeiten, daher teilt ein niedrigeres Limit dem Indexer mit, früher auf die Festplatte umzuschalten und somit weniger Speicher zu verwenden. Versuchen Sie 10.000 oder sogar noch kleinere Zahlen.
4.  Ändern Sie die Datenbank-Engine für die Tabellen *__finder_tokens* und *#__finder_tokens_aggregate* von MEMORY auf InnoDB. Dies könnte zwar die Leistung ernsthaft beeinträchtigen, da ein größerer Teil des Indexierungsprozesses die Festplatte statt des Speichers verwenden wird, könnte aber dem Indexer ermöglichen, fertig zu werden, ohne den Speicher zu überlasten. Erwarten Sie jedoch, dass der Indexierungsprozess viel länger dauert. Die Suchleistung wird dadurch jedoch nicht beeinträchtigt.
5.  Versuchen Sie zu ermitteln, welche Inhaltsobjekte den Indexer zum Überlasten des Speichers bringen. Wenn es nicht offensichtlich ist, versuchen Sie, alle Smart Search Plugins außer einem zu deaktivieren. Wenn der Indexer jeweils nur mit einem aktivierten Plugin läuft, sollte das Aufschluss darüber geben, welche Inhaltsart(en) das Problem verursachen. Als letzte Möglichkeit sollten Sie erwägen, einige außergewöhnlich große Inhaltsobjekte in separate Beiträge aufzuteilen. Wenn das Problem bei einem benutzerdefinierten Inhaltstyp liegt, sehen Sie sich den Plugin-Code an und erwägen Sie, weniger von den verfügbaren Inhalten pro Objekt zu indexieren.

## Probleme mit unzureichendem Speicherplatz

Die Smart Search-Indextabellen können schnell wachsen! Die Tabellen *_#finder_links_termsX* (wobei *X* ein einzelnes hexadezimales Zeichen ist) enthalten eine Zeile pro Begriff/Ausdruck und pro Inhaltelement. Ein einzelner Joomla-Beitrag mit 1000 Wörtern führt typischerweise dazu, dass diesen Tabellen etwa 3000 Zeilen hinzugefügt werden. Ein zweiter Beitrag ähnlicher Größe fügt eine ähnliche Anzahl von Zeilen hinzu, selbst wenn beide Beiträge dieselben Wörter enthalten. Eine Website mit zehntausenden von Beiträgen, von denen einige möglicherweise Tausende von Wörtern enthalten, endet wahrscheinlich damit, dass diese Zuordnungstabellen Millionen von Zeilen enthalten. Es ist nicht ungewöhnlich, dass die Indextabellen unter solchen Umständen mehrere Gigabyte Speicherplatz beanspruchen.

Mit der aktuellen Version von Smart Search können Sie nicht viel dagegen tun. Es wird jedoch gehofft, dass Sie in der nächsten Version die Anzahl der Wörter pro Ausdruck, die indexiert werden, anpassen können. Derzeit ist dies fest auf 3 eingestellt, was bedeutet, dass jedes Wort, das indexiert wird, auch als Teil eines Paares benachbarter Wörter und als Teil eines Dreiers benachbarter Wörter indexiert wird. Dies ist nützlich für die Autovervollständigungsfunktion und verbessert allgemein die Qualität der Suchergebnisse. Auf Websites, bei denen Speicherplatz ein Problem darstellt, wäre es gut, dies auf 2 oder sogar 1 zu reduzieren, damit die Zuordnungstabellen entsprechend kleiner wären.

## Anmerkungen

1.  Derzeit gibt es keine gleichzeitige Sperrung, um zu verhindern, dass mehr als ein Prozess den Indexer gleichzeitig ausführt. Dies wird fast mit Sicherheit zu einem beschädigten Index führen. Selbst wenn jemand Änderungen an einem Inhaltselement speichert, während ein vollständiger Indexvorgang durchgeführt wird, könnte dies potenziell den Index beschädigen.

*Übersetzt von openai.com*

