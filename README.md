![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# LAB | #Versprich mir ein Abendessen

## Einführung

Aufgrund der asynchronen Natur von JavaScript sind Versprechen und Rückrufe sehr wichtig. Beide ermöglichen es uns, den Ablauf der Operationen zu steuern und Aufgaben in Sequenz auszuführen.

<p align="center">   
<img src="https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-cover.png" alt="Lab Promise me dinner - final result" width="500" />   
</p>   

## Anforderungen

- Fork dieses Repo.
- Clone es auf Deine Maschine.

## Abgabe

Nach Abschluss führe die folgenden Befehle aus:

```shell 
$ git add .
$ git commit -m "done"
$ git push origin master  
```   
Erstelle einen Pull Request, damit deine TAs deine Arbeit überprüfen können.

## Anleitung

### Iteration 0 | Der Starter-Code

Wir haben dir einen Starter-Code bereitgestellt:

- `javascript/data.js` - enthält vier Arrays mit Schritten zur Zubereitung von 4 verschiedenen Lebensmitteln: _Kartoffelpüree_, _Steak_, _Rosenkohl_ und _Brokkoli_.

- `javascript/getInstruction.js` - enthält eine Funktion **`getInstruction`**, die **Rückrufe verwendet**, um asynchron Anweisungsschritte für jedes Lebensmittel abzurufen. Es verwendet `setTimeout`, um eine asynchrone Operation zu simulieren.

 ```js    
  getInstruction(food, step, callback, errorCallback)    
``` 
:exclamation: **Du solltest in dieser Datei keine Änderungen vornehmen.**


- `javascript/obtainInstruction.js` -hat eine Funktion **`obtainInstruction`**, die **Versprechen verwendet**, um asynchron Anweisungsschritte für jedes Lebensmittel abzurufen. Es verwendet ebenfalls `setTimeout`, um eine asynchrone Operation zu simulieren.

 ```js    
obtainInstruction(food, step) 
```  
:exclamation: **Du solltest in dieser Datei keine Änderungen vornehmen.**


- `javascript/index.js` - in dieser Datei haben wir ein Beispiel hinterlassen, um dir zu zeigen, wie der Code ausgeführt werden sollte. Die bereitgestellte Code verwendet jedoch noch keine verschachtelten Rückrufe oder Versprechen, weshalb die Schritte nicht in der richtigen Reihenfolge gedruckt werden. Deine Aufgabe in der ersten Iteration wird sein, dies richtig zu machen, aber dazu später mehr.

- `index.html` - enthält eine Basis-HTML-Struktur, die benötigt wird, daher muss kein Code dort hinzugefügt werden. Die zuvor genannten JavaScript-Dateien sind bereits mit dem `index.html` verlinkt. Die `data.js` wird zuerst geladen, um sicherzustellen, dass die Arrays, die Anweisungen enthalten, bereits geladen sind und in anderen Dateien verwendet werden können, in denen wir sie benötigen.

  :exclamation: **Du solltest in dieser Datei keine Änderungen vornehmen.**



### Nicht synchronisiert

**Du solltest deinen Code <u>nur</u> in der Datei `javascript/index.js` schreiben.**  

Öffne jetzt die Datei und schaue dir den bereitgestellten Startercode an. Der bereitgestellte Code verwendet keine verschachtelten Rückrufe, um eine Sequenz der Ausführung durchzusetzen, weshalb die Schritte nicht in der richtigen Reihenfolge angezeigt werden.

Öffne nun die `index.html` Seite im Browser. Beachte, wie die Kochschritte in der falschen Reihenfolge angezeigt werden.


<details>    
 <summary><b>Screenshot</b></summary>   

![Steps out of sync](https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-out-of-sync.gif)  

</details>   


:exclamation: Bevor du mit Iteration 1 beginnst, kommentiere den ursprünglichen Code in `javascript/index.js` aus.

<br>   

## Iteration 1 | Mache Püree mit Callbacks

Verwende verschachtelte Callbacks, um die Kochschritte zur Herstellung von Püree in der richtigen Reihenfolge auszugeben. Schreibe deinen JavaScript-Code in die bereitgestellte Datei `javascript/index.js`. Nochmals die Erinnerung, die Datei `getInstruction.js` nicht zu ändern.

```javascript 
// Iteration 1 - using callbacks 
getInstruction('mashedPotatoes', 0, (step0) => {    
  document.querySelector("#mashedPotatoes").innerHTML += `<li>${step0}</li>` 
    // ... Your code here 
    // ...
}); 
```   


Nach dem letzten Schritt sollte ein zusätzliches `<li>` mit dem Text `Mashed potatoes are ready!` angezeigt werden.


<details>    
 <summary><b>Erwartetes Ergebnis</b></summary>   

![Iteration 1 expected result](https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-1-result.gif)

</details>   


## Iteration 2 | Zubereitung des Steaks mit Promises


Mit Promises und der `then()`-Anweisung sollst Du die Anweisungen zur Anzeige der Kochanleitung für das Steak in der richtigen Reihenfolge ausgeben. Dieses Mal musst Du die Funktion `obtainInstruction` aufrufen, die ein ausstehendes Promise zurückgibt.

Arbeite weiterhin in der `javascript/index.js`. Du solltest die `obtainInstruction.js`-Datei nicht ändern.

```javascript 
// Iteration 2 - using promises 
obtainInstruction('steak', 0)    
 .then( (step0) => { 
  document.querySelector("#steak").innerHTML += `<li>${step0}</li>` 
  //  ... Your code here 
  }) 
  
  // ... Your code here  
 ```   

Nach dem letzten Schritt sollte ein zusätzliches `<li>` mit dem Text `Stake is ready!` angezeigt werden.



<details>    
 <summary><b>Erwartetes Ergebnis</b></summary>  

![Iteration 2 expected result](https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-2-result.gif)

</details>   


## Iteration 3 | Brokkoli mit async/await zubereiten

Verwende Promises mit der `async` und `await` Syntax, um die Anweisungen zur Zubereitung von Brokkoli in der richtigen Reihenfolge auszugeben. Du benötigst dafür die Funktion `obtainInstruction`, die ein ausstehendes Promise zurückgibt.

```javascript 
async function makeBroccoli() {
  // ... Your code here
}
```   

Nach dem letzten Schritt solltest du ein zusätzliches `<li>` mit dem Text `Broccoli is ready!` anzeigen.



<details>    
 <summary><b>Erwartetes Ergebnis</b></summary>   

![Iteration 3 expected result](https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-3-result.gif)

</details>   


## Bonus 1

When das jeweilige Essen fertig ist (alle Schritte aufgelistet sind), entferne das `hidden`-Attribut aus dem `<img/>`-Element, das das Essen repräsentiert, sodass das Bild angezeigt wird.



<details>    
 <summary><b>Erwartetes Ergebnis</b></summary>   

![Bonus Iteration 1 expected result](https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-bonus-1-result.gif)

</details>   

## Bonus 2

Verwende `Promise.all`, um die Kochschritte zur Herstellung von Rosenkohl in der richtigen Reihenfolge anzuzeigen.

Nach dem letzten Schritt sollte ein zusätzliches `<li>` mit dem Text angezeigt werden: `Brussels sprouts are ready!`.

**Das Endergebnis sollte wie folgt aussehen - mit allen Kochschritten, die in der richtigen Reihenfolge angezeigt werden**:

![Bonus Iteration 2 expected result](https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/labs/lab-promise-me-dinner-bonus-2-result.gif)

<br>   

**Viel Spaß beim Coden!** :blue_heart: