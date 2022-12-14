## Befehle
- Befehle in RISC-V sind stets 32 Bit gross und decken arithmetische, logische, Sprung- und Speicheroperationen ab
#### Befehlskodierung
- Unterschiedliche Befehle verwenden unterschiedliche Operanden, weshalb Befehle, ausgehend vom Opcode in verschiedene Instruktionsformate unterteilt werden
	- R-Typ (Register-zu-Register Operationen)
	- I-Typ (Immediate Operationen und Ladebefehle)
	- U-Typ (Operationen mit Long Immediates)
	- S-Typ (Speichern von Datenwoerten)
	- B-Typ (Bedingte Spruenge)
	- J-Typ (Unbedingte Spruenge und Unterprogrammaufrufe)
### Konstanten
- Immediates in einem RISC-V Befehl koennen nur in 12 Bits kodiert werden
- Um groessere Konstanten in einem Register zu speichern, werden ueber lui die oberen 20 Bits eines Registers mit Werten gefuellt
- Die unteren 12 Bits koennen nun regulaer besetzt werden
###### Beispiel
![[Pasted image 20221206001128.png]]
## Register
- Einem RISC-V Computer stehen 32 Register zur Verfuegung
- Jedes Register hat eine Breite von 4 Bytes
- Diese Register koennen als Speicher fuer temporaere Werte und Ruecksprungadressen dienen
#### Beispiel
![[Pasted image 20221205124540.png]]
## Speicher
- Der Speicherbedarf eines RISC-V Programms kann potentiell die Anzahl der Register ueberschreiten
- Zusaetzliche Daten koennen in einem separaten Speicher gehalten werden
- Da dieser Speicher nur eine Breite von einem Byte hat, nimmt ein Registerwert 4 Speicherzeilen in Anspruch
#### Speicherzugriff
###### Lesezugriff
- Von einer Speicheradresse kann ueber den lw Befehl gelesen werden
- Hierbei wird als Ziel ein Register und als Quelle eine Adresse mit einem Offset gewaehlt
- Um einen Speicherzugriff durchzufuehren, muss somit ebenfalls eine Addition erfolgen
###### Schreibzugriff
- Parallel zu lw kann mit sw ein Registerinhalt in eine Speicheradresse geschrieben werden
###### Beispiel
![[Pasted image 20221205125448.png]]
![[Pasted image 20221205125459.png]] 
#### Beispiel
![[Pasted image 20221205131215.png]]