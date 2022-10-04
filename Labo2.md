# Labo 2 



<div id="top"></div>

<details>
  <summary>Inhoudstafel</summary>
  <b> Variabelen: </b>
	<ol>
		<li>
		<a href="#oefening1">Oefening 1</a>
		</li>
        </ol>
	<b>Variabelen in scripts: </b>
	<ol>
		<li>
		<a href="#oefening2">Oefening 1</a>
		</li>
		<li>
		<a href="#oefening3">Oefening 2</a>
		</li>
		<li>
		<a href="#oefening4">Oefening 3</a>
		</li>
		<li>
		<a href="#oefening5">Oefening 4</a>
		</li>
		<li>
		<a href="#oefening6">Oefening 5</a>
		</li>
		<li>
		<a href="#oefening7">Oefening 6</a>
		</li>
	</ol>
	<b>Eigenaars en groepseigenaars veranderen: </b>
	<ol>
		<li>
		<a href="#oefening8">Oefening 1</a>
		</li>
		<li>
		<a href="#oefening9">Oefening 2</a>
		</li>
		<li>
		<a href="#oefening10">Oefening 3</a>
		</li>
		<li>
		<a href="#oefening11">Oefening 4</a>
		</li>
		<li>
		<a href="#oefening12">Oefening 5</a>
		</li>
		<li>
		<a href="#oefening13">Oefening 6</a>
		</li>
		<li>
		<a href="#oefening14">Oefening 7</a>
		</li>
		<li>
		<a href="#oefening15">Oefening 8</a>
		</li>
		<li>
		<a href="#oefening16">Oefening 9</a>
		</li>
		<li>
		<a href="#oefening17">Oefening 10</a>
		</li>
		<li>
		<a href="#oefening18">Oefening 11</a>
		</li>
		<li>
		<a href="#oefening19">Oefening 12</a>
		</li>
	</ol>
</details>

<div id="oefening1"> </div>

# Variabelen:

## Oefening 1:
- PATH
- HISTSIZE
- UID
- HOME
- HOSTNAME
- LANG
- USER
- OSTYPE
- PWD

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening2"> </div>



# Variabelen in scripts:

## Oefening 1:
1.Op een Linux-systeem van de Debian-familie kan je een lijst van geïnstalleerde software opvragen met het commando apt list --installed. Doe dit op jouw Linux-Mint VM. Het commando genereert heel wat output, zo veel dat je misschien zelfs niet de volledige lijst kan zien in de terminal. Zorg er voor dat je telkens een pagina te zien krijgt en dat je op spatie kan drukken voor de volgende pagina. <br> `osboxes@osboxes:~$ apt list --installed | more`  of less, nog beter.

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening3"> </div>

## Oefening 2:
2. Als we verschillende dingen willen doen met de lijst van geïnstalleerde software, dan moeten we het commando telkens opnieuw uitvoeren. Dat is tijdrovend. Schrijf in plaats daarvan het resultaat van het commando weg in een bestand packages.txt.
<br> `osboxes@osboxes:~/Documents/Labo2$ apt list --installed > packages.txt`
<br> Warning code: WARNING: apt does not have a stable CLI interface. Use with caution in scripts. 

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening4"> </div>

## Oefening 3:
3. Bij het wegschrijven naar een bestand krijg je toch nog een waarschuwing te zien. Zorg er voor dat deze niet getoond wordt.
<br> `osboxes@osboxes:~/Documents/Labo2$ apt list --installed > packages.txt 2> /dev/null`

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening4"> </div>

## Oefening 4:
4. Toon de eerste tien lijnen van packages.txt (met het geschikte commando!). De eerste lijn bevat nog geen naam van een package en hoort er dus eigenlijk niet bij. Gebruik een geschikt commando om er voor te zorgen dat die eerste lijn uit de uitvoer van apt list niet mee weggeschreven wordt naar packages.txt. Controleer het resultaat!
<br> `osboxes@osboxes:~/Documents/Labo2$ head -10 packages.txt | tail -9`

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening5"> </div>

## Oefening 5:
5. Gebruik een geschikt commando om te tellen hoeveel packages er momenteel geïnstalleerd zijn. Tip: elke lijn van packages.txt bevat de naam van een package.

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening6"> </div>


