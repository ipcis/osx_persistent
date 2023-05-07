Hier ist ein Beispielcode, der eine Property-List-Datei in das Verzeichnis "~/Library/LaunchAgents" des aktuellen Benutzers schreibt:

```python
import os
import plistlib

# Pfad zur Property-List-Datei, die wir erstellen möchten
plist_path = os.path.expanduser('~/Library/LaunchAgents/com.example.myscript.plist')

# Inhalt der Property-List-Datei
plist_content = {
    'Label': 'com.example.myscript',
    'Program': '/path/to/myscript.py',
    'RunAtLoad': True,
    'KeepAlive': True
}

# Property-List-Datei schreiben
with open(plist_path, 'wb') as file:
    plistlib.dump(plist_content, file)

print(f'Property-List-Datei erfolgreich erstellt: {plist_path}')
```

Dieser Code erstellt eine Property-List-Datei mit dem Namen "com.example.myscript.plist" im Verzeichnis "~/Library/LaunchAgents" des aktuellen Benutzers. Die Datei enthält einige Eigenschaften, darunter den Namen des Programms, das ausgeführt werden soll ("Program"), ob das Programm beim Start ausgeführt werden soll ("RunAtLoad") und ob es am Leben gehalten werden soll, wenn es abstürzt ("KeepAlive"). Natürlich müssen Sie den Pfad zu Ihrem eigenen Skript in der "Program"-Eigenschaft ersetzen.
