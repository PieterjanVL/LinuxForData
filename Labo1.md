# Labo 1  



<div id="top"></div>

<details>
  <summary>Inhoudstafel</summary>
  <b> Gebruikers en groepen aanmaken: </b>
	<ol>
		<li>
		<a href="#oefening1">Oefening 1</a>
		</li>
		<li>
		<a href="#oefening2">Oefening 2</a>
		</li>
		<li>
		<a href="#oefening3">Oefening 3</a>
		</li>
		<li>
		<a href="#oefening4">Oefening 4</a>
		</li>
		<li>
		<a href="#oefening5">Oefening 5</a>
		</li>
		<li>
		<a href="#oefening6">Oefening 6</a>
		</li>
		<li>
		<a href="#oefening7">Oefening 7</a>
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

# Gebruikers en groepen aanmaken:

## Oefening 1:
 1. Wat is het commando om de huidige directory op te vragen? In welke map bevind je jou nu? <br>
`osboxes@osboxes:~$ pwd \ antwoord: /home/osboxes`

 2. Wat is het UID van deze gebruiker, wat is de GID?     
 `osboxes@osboxes:~$ cat /etc/passwd` <br> geeft: `osboxes:x:1000:1000:osboxes.org,,,:/home/osboxes:/bin/bash` <br> Antwoord: UID= 1000 en GID= 1000
 <br> <br> Meer juister antwoord zou zijn:  <br> `osboxes@osboxes:~$ id` <br> output: `uid=1000(osboxes) gid=1000(osboxes) groups=1000(osboxes),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),115(lpadmin),135(sambashare)` <br> antwoord blijft hetzelfde! 

 <p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening2"> </div>

## Oefening 2:
`osboxes@osboxes:~$ sudo adduser alice 
[sudo] password for osboxes:           
Adding user alice' ...
Adding new group alice' (1001) ...
Adding new user alice' (1001) with group alice' ...
Creating home directory /home/alice' ...
Copying files from /etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for alice
Enter the new value, or press ENTER for the default
	Full Name []: 
	Room Number []: 
	Work Phone []: 
	Home Phone []: 
	Other []: 
Is the information correct? [Y/n] y
osboxes@osboxes:~$ 
`
wachtwoord: hogent2022

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening3"> </div>

## Oefening 3:
1. In welk bestand kan je de UID, gebruikersnaam, homedirectory, enz. van alle gebruikers terugvinden? <br> `osboxes@osboxes:~$ cat /etc/passwd `

2. In welk configuratiebestand kan je al de bestaande gebruikersgroepen nakijken, en ook de gebruikers die lid zijn van elke groep? <br> `osboxes@osboxes:~$ cat /etc/group `


3. In welk configuratiebestand vind je de wachtwoorden van alle gebruikers? <br> `osboxes@osboxes:~$ sudo cat /etc/shadow `

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening4"> </div>

## Oefening 4:
1. Maak een groep aan met de naam sporten <br> `osboxes@osboxes:~$ sudo groupadd sporten `

2. In welk configuratiebestand vind je het GID van deze groep terug? <br> `osboxes@osboxes:~$ cat /etc/group ` sporten:x:1002:

3. Wat zal het GID zijn van de groepen zwemmen en judo als je deze nu onmiddellijk zou aanmaken? Maak ze aan en controleer! <br> `1003 en 1004, zwemmen:x:1003:
judo:x:1004:`

4. Voeg de gebruiker alice toe aan de groepen sporten en zwemmen <br>`osboxes@osboxes:~$ sudo usermod  -aG sporten alice` <br>
`osboxes@osboxes:~$ sudo usermod -aG judo alice`
<br> resultaat: `uid=1001(alice) gid=1001(alice) groups=1001(alice),1002(sporten),1003(zwemmen)`

5. Log in als alice door in een terminal het commando su - alice (let op de spaties!) uit te voeren <br> `osboxes@osboxes:~$ su - alice`

6. Zorg er nu voor dat de groep sporten de primaire groep wordt van alice. <br> `osboxes@osboxes:~$ sudo usermod -g sporten alice`

7. Zorg er voor dat alice uitgelogd is, ga terug naar root <br> `osboxes@osboxes:~$ logout`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening5"> </div>

## Oefening 5 : 
1. Geef de gebruikte commando's om de gebruikers aan te maken en ook om te verifiëren of dit correct gebeurd is: <br>  <br>
`osboxes@osboxes:/home$ sudo adduser --ingroup sporten bob` <br> toevoegen aan judo: `osboxes@osboxes:/home$ sudo usermod -a -G judo bob ` <br>
 als we nu de de info opvragen van bob: `osboxes@osboxes:/home$ id bob `<br>
`uid=1002(bob) gid=1002(sporten) groups=1002(sporten),1004(judo)` <br>
<b>Wachtwoord bob en alle andere: </b> p

2. Verwijder nu de groep alice en controleer: <br> `osboxes@osboxes:~$ sudo groupdel alice`

3. Gebruiker daniel gaat een tijdje niet meer sporten. Zorg er voor dat deze gebruiker tot nader order geen toegang meer kan hebben tot het systeem (zonder het wachtwoord of de gebruiker te verwijderen!). <br>
`osboxes@osboxes:~$ sudo usermod -L daniel`

4. Hoe kan je controleren dat daniel inderdaad geen toegang meer heeft tot het systeem? In welk bestand kan dat en hoe zie je daar dan dat het account afgesloten is? <br>
`osboxes@osboxes:/home$ sudo grep daniel /etc/shadow` <br> retourneert gehaste ww met een ! zo weten we dat het acc is geblokt ervoor: `daniel:!$6$Ym6uZZ0XYOQPHSu0$vExzXTg31/seg4aFd1HKoiQAY17r4U5JSCtK6FSR9EQJfp3oVy8iBTH6U1PTsioB9uSlheEWWqWsaB8uLT8Ul.:19266:0:99999:7:::`

5. Gebruiker daniel komt terug naar de sportclub. Geef hem opnieuw toegang tot het systeem. <br>
`osboxes@osboxes:/home$ sudo usermod -U daniel` <br> Nu gaan we terug kijken naar het ww en zien we dat ! weg is: `osboxes@osboxes:/home$ sudo grep daniel /etc/shadow
daniel:$6$Ym6uZZ0XYOQPHSu0$vExzXTg31/seg4aFd1HKoiQAY17r4U5JSCtK6FSR9EQJfp3oVy8iBTH6U1PTsioB9uSlheEWWqWsaB8uLT8Ul.:19266:0:99999:7::: `

6. Gebruiker eva stopt helemaal met sporten. Verwijder deze gebruiker, maar doe dit zorgvuldig: zorg er in het bijzonder voor dat ook haar homedirectory verwijderd wordt. <br>
`osboxes@osboxes:/home$ sudo userdel -r eva`

7. Log aan als de gebruiker carol: <br> `osboxes@osboxes:/home$ su - carol` <br> 
		
	1.  Controleer of je in de “thuismap” bent van deze gebruiker. Maak onder deze map een bestand test aan door middel van het commando touch. <br>  `carol@osboxes:~$ pwd /home/carol` <br> `carol@osboxes:~$ touch test.txt`

	2. Probeer nu als gebruiker carol je te verplaatsen naar de “thuismap” van alice. <br> `carol@osboxes:/home$ cd alice ` <br> ` carol@osboxes:/home/alice$ `

	3. Kan je de inhoud van de mappen binnen de thuismap van alice bekijken? <br> We kunnen als Carol zijnde de inhoud van de home map van alice bekijken. Dwz we kunnen de bestanden zien en readen die zich in /home/alice bevinden. Wat we niet kunnen doen als Carol bij Alice is de inhoud van bestanden aanpassen als we dat proberen met vim krijgen we deze error: <br> `E45: 'readonly' option is set (add ! to override) `

	4. Probeer nu als carol onder de “thuismap” van alice ook een bestand test te maken. Lukt dit? Kan je dit verklaren? <br> Neen dit gaat niet omdat we de juiste rechten niet hebben: <br>
	`carol@osboxes:/home/alice$ touch testCarol.txt` <br> `touch: cannot touch 'testCarol.txt': Permission denied` <br> als we kijken naar de permissions van /home/alice zien we: <br> 
	`carol@osboxes:/home$ ls -l ` <br> `total 40 drwxr-xr-x  5 alice   sporten  4096 Oct  1 05:57 alice`
	<br> <b>Conclusie: </b> we zien dat we niet de juiste rechtn hebben om als Carol bestanden aan te maken en te wijzigen bij Alice

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening6"> </div>

## Oefening 6:
1. Bekijk de eerste regels van het bestand /etc/shadow. Wat bemerk je bij de gebruiker root? <br> 
`osboxes@osboxes:~$ sudo cat /etc/shadow [sudo] password for osboxes:   `   <br> `root:!:19007:0:99999:7:::
` <br> We zien dat het wachtwoord met een ! begint, ik denk dat het wachtwoord geblokkeert staat.

2. Log in als de root-gebruiker met het commando sudo -i <br> `osboxes@osboxes:~$ sudo -i
[sudo] password for osboxes:`

	1. Wat is de home-directory van root? <br> `root@osboxes:~# pwd /root`

	2. Wat is het UID van deze gebruiker, wat is de GID? <br> `root@osboxes:~# id root uid=0(root) gid=0(root) groups=0(root)`

3. Stel, nog steeds ingelogd als root, een wachtwoord in voor root. Kies een uniek, nieuw wachtwoord!
Merk je de verandering in /etc/shadow? <br> `root@osboxes:~# passwd 
New password: 
Retype new password: 
passwd: password updated successfully
root@osboxes:~# cat /etc/shadow
root:$6$KYZO.OC7HcdOHN4B$ui77VZM7uYFslcfLeuipCExq98NREQIZnfKm96W8ArwgzNeAqnS7xnIbzdjQmNvQJTI5CpE32J3gP9P/Gvm7r0:19266:0:99999:7:::`
<br> Ja we zien dat er geen ! meer voor het ww staat van root, ww = root

4. Log in als de root-gebruiker met het commando su - (let op de spatie!) <br> `osboxes@osboxes:~$ su -`
<br> We moeten hier het wachtwoord ingeven van de root die we daarnet hebben veranderd naar ww root

5. Log uit, en log opnieuw in met sudo su -. Wat wordt er anders? <br> `osboxes@osboxes:~$ sudo su -`
<br> `[sudo] password for osboxes: `
<br> Hierbij loggen we in via user osboxes dus hebben we ook het wachtwoord van de user osboxes nodig namelijk hogent. <br> <br><b>Het verschil: </b> <br> Met su - loggen we in om root te worden met het wachtwoord van de root in mijn geval ook root. Met sudo su - willen we ook root worden maar dit gebeurt via de user osboxes dus hebben we het wachtwoord van de user osboxes nodig namelijk hogent2022. Voila we zijn via beide manieren admin geworden!

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening7"> </div>

## Oefening 7:
1. Voeg jezelf (met je eigen gekozen loginnaam) toe aan de VM waarin we werken. Gebruik hiervoor useradd -m <jouw loginnaam> <br> `osboxes@osboxes:/home$ sudo useradd -m pj`

2. Bewerk /etc/passwd zodat je ook bash gebruikt als default shell. <br> `osboxes@osboxes:/home$ sudo usermod -s /bin/bash pj`

3. Bekijk /etc/shadow. Bemerk dat jijzelf als gebruiker nog geen wachtwoord hebt! Stel het in met passwd
<br> Zonder ww: `pj:!:19266:0:99999:7:::` <br> Toevoegen ww: `osboxes@osboxes:/home$ sudo passwd pj
New password: 
Retype new password: 
passwd: password updated successful` <br> Daarna bekijken we /etc/shadow nog is: `pj:$6$/bv5MxATaEk5cfZk$1QIlhTXeACTEzbYEdlH8CYRXYri7TBoSNBaYYdshIReqMN3oZOSoRC4foHVQ59jNANQjKpJtPVcBPcdDbBL4x1:19266:0:99999:7::: `

4. Nu wil je jezelf eveneens adminstrator van het systeem maken, zodat je met sudo beheerstaken kan uitvoeren. Aan welke groep voeg je jezelf hiervoor toe?
Hint: https://www.ibm.com/docs/en/cabi/1.1.4?topic=premises-configuring-sudo-access-users
<br> Eerst: `osboxes@osboxes:~$ sudo visudo` dit opent vervolgens: <br> `  GNU nano 4.8                    /etc/sudoers.tmp                              
	Host alias specification

	User alias specification

	Cmnd alias specification

	User privilege specification
	root    ALL=(ALL:ALL) ALL

	Members of the admin group may gain root privileges
	%admin ALL=(ALL) ALL

	Allow members of group sudo to execute any command
	%sudo   ALL=(ALL:ALL) ALL

	See sudoers(5) for more information on "#include" directives:

	includedir /etc/sudoers.d `

<br><b> Antwoord:  </b>  Dan zien we dat user pj(ik) toegevoegd moet worden bij groep sudo <br>
`osboxes@osboxes:~$ sudo usermod -aG sudo pj`

<p align="right">(<a href="#top">back to top</a>)</p>

# Eigenaars en groepseigenaars veranderen:

<div id="oefening8"> </div>

## Oefening 1:
1. Maak als root onder /srv/ twee directories aan met de naam groep/verkoop/ en groep/inkoop/. Maak ook 2 groepen aan met de namen verkoop en inkoop. Maak twee gebruikers aan, margriet met primaire groep verkoop en roza, die als primaire groep inkoop heeft. Zorg dat de groepen eigenaar zijn van de overeenkomstige directories en dat margriet eigenaar is van directory verkoop en roza van het directory inkoop. Geef de gebruikte commando’s en controleer: <br> <br>aanmaken groepen:  `root@osboxes:/srv/groep# mkdir verkoop en
root@osboxes:/srv/groep# mdir inkoop` <br> `osboxes@osboxes:~$ sudo addgroup verkoop Adding group verkoop' (GID 1001) ...
Done.
osboxes@osboxes:~$ sudo addgroup inkoop
Adding group inkoop' (GID 1005) ...
Done.
` Wachtwoord beide = p
<br> <br> Aanmaken users roza en margriet plus toevoegen aan juiste groep `sudo adduser --ingroup inkoop roza` <br> `osboxes@osboxes:~$ id roza
uid=1007(roza) gid=1005(inkoop) groups=1005(inkoop)` <br> <br> Groepen eigenaar maken van hun map: <br>Op dit moment is degene die de dir heeft aangemaakt owner in ons geval root: 
`drwxr-xr-x 2 root root 4096 Oct  1 09:50 inkoop
en drwxr-xr-x 2 root root 4096 Oct  1 09:50 verkoop
` <br>We gaan nu de groepen en user owners maken van hun directory dus verkoop moet owner van zijn map idem voor inkoop. Ook moet Margriet owner worden van de dir verkoop en roza van inkoop: `root@osboxes:/srv/groep# sudo chown margriet:verkoop verkoop` <br> Resulteert in: `drwxr-xr-x 2 margriet verkoop 4096 Oct  1 09:50 verkoop`



<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening9"> </div>

## Oefening 2:
2. Zorg ervoor dat gebruikers en groepen uit de vorige stap alle permissies hebben. Geef het geschikte commando en controleer. <br> `root@osboxes:/srv/groep# chmod 775 verkoop` <br> Resulteert in: `drwxrwxr-x 2 margriet verkoop 4096 Oct  1 09:50 verkoop`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening10"> </div>

## Oefening 3:

3. Voeg een gebruiker, vb alice, toe aan de groep inkoop en verkoop en controleer. Geen van beide groepen zijn primair. <br> `root@osboxes:/srv/groep# usermod -aG verkoop alice` <br>Controle:  `root@osboxes:/srv/groep# id alice
uid=1001(alice) gid=1002(sporten) groups=1002(sporten),1003(zwemmen),1001(verkoop),1005(inkoop)
root@osboxes:/srv/groep# groups alice
alice : sporten zwemmen verkoop inkoop
`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening11"> </div>

## Oefening 4:

4. Log in als alice en ga naar de directory verkoop. Laat de gebruiker hier een leeg bestand, bestand1, aanmaken in de directory verkoop. (Indien je hier problemen ondervindt, log dan in via een andere terminalvenster). <br> `alice@osboxes:/srv/groep/verkoop$ touch bestand1.txt
`
<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening12"> </div>

## Oefening 5:

5. Wie is nu eigenaar van bestand1 en wie de groepseigenaar? <br> `-rw-r--r-- 1 alice sporten 53 Oct  1 10:23 bestand1.txt` <br> We zien dat de user owner alice is en alice haar primaire groep wat op dat moment zwemmen was is de group owner van het bestand1.txt.

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening13"> </div>

## Oefening 6:

6. Zorg er nu voor dat de groepseigenaar van de directory verkoop automatisch de groepseigenaar wordt van alle bestanden en directories die onder verkoop gemaakt worden. Geef de gebruikte commando’s. <br> `root@osboxes:/srv/groep# chmod 2775 verkoop`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening14"> </div>

## Oefening 7:

7. Doe hetzelfde voor de directory inkoop. Geef de gebruikte commando’s. <br> `root@osboxes:/srv/groep# chmod 2775 inkoop`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening15"> </div>

## Oefening 8:

8. Verander opnieuw naar gebruiker alice en laat deze gebruiker een leeg bestand2 aanmaken in de directory verkoop. Geef de gebruikte commando’s. <br> `alice@osboxes:/srv/groep/verkoop$ touch bestand2.txt` <br>Dit resulteert in na ls -l: `-rw-r--r-- 1 alice verkoop 72 Oct  1 10:38 bestand2.txt
` <br> We zien idd dat de groepowner automatisch verkoop is gewoorden van bestand2. Dit komt omdat de groepowner van de dir nu automatisch groupowner wordt van al de nieuwe bestand in zijn directory.


<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening16"> </div>

## Oefening 9:

9. Wie is nu eigenaar van bestand2 en wie groepseigenaar?
<br> Userowner: Alice
<br> Groupowner: verkoop
<br> `-rw-r--r-- 1 alice verkoop 72 Oct  1 10:38 bestand2.txt`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening17"> </div>

## Oefening 10:

10. Laat nu gebruiker margriet een leeg bestand bestand3 aanmaken. Controleer de eigenaar van bestand3 en de groepseigenaar.Aanmaken bestand als Margriet: <br> `margriet@osboxes:/srv/groep/verkoop$ touch bestand3.txt`
<br> `-rw-r--r-- 1 margriet verkoop  0 Oct  1 10:45 bestand3.txt` <br> Groepseigenaar: verkoop

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening18"> </div>

## Oefening 11:

11. Laat nu gebruiker alice bestand3 verwijderen. Lukt dit?
<br> `alice@osboxes:/srv/groep/verkoop$ rm bestand3.txt` <br>
`rm: remove write-protected regular empty file 'bestand3.txt'? yes
`
<br>Conclussie: Ja dit lukt.
<br> Controle: `alice@osboxes:/srv/groep/verkoop$ ls
bestand1.txt  bestand2.txt`

<p align="right">(<a href="#top">back to top</a>)</p>

<div id="oefening19"> </div>

## Oefening 12:

12. Zorg er nu voor dat de gebruikers elkaars bestanden niet kunnen verwijderen. Als de gebruiker echter eigenaar is van het betreffende directory mag dit wel. Leg uit hoe je dit doet en controleer. Schrijf je gevolgde procedure op.

<p align="right">(<a href="#top">back to top</a>)</p> <p align="left">(<a href="#top">Volgend Labo</a>)</p> <p align="center">(<a href="https://pieterjanvl.github.io/LinuxForData/">Home</a>)</p>