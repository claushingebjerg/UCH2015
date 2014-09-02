


Kursus.uch.dk
===========================

Backend
-------

### Import af kurser ###
Kurser importeres via W005 KursusudbudViaWeb webservicen udbudt af Uni-C.  
(http://www.admsys.uni-c.dk/EASY-A/Webservices#W005 KursusudbudViaWeb).  
Importen sker via en specialprogrammeret applikation implementeret i Umbraco.  
Importen køres x antal gange i døgnet..XXXXxxxx

### Manuel oprettelse af kurser ###
Udover kurser importeret fra web servicen er det mulig at oprette kurser manuelt.  
Dette gøres som ved normal oprettelse af sider i umbraco.

### Dokumenttyper ###
Kurserne importeres som noder/sider i umbraco, med hold som subnoder.  
Dette danner grundlag for de enkelte kursussider.

![Kursus træ](images/kursustree.png)

Der oprettes to dokumenttyper, "Kursus" og "Hold"


### Dokumenttype - "Kursus" ###
Hvert kursus bliver oprettet som en selvstændig side/node.  
På hvert kursus findes er der mulighed for at skrive en artikel samt tilkoble et billede.

####Kursus artikel####


![Kursus artikel](images/kursusartikel.png)

<table>
	<tr>
		<th>Felt</th>
		<th>Felttype</th>
	</tr>
	<tr>
		<td>Kursus artikel</td>
		<td>Tab</td>
	</tr>
	<tr>
		<td>Billede	</td>
		<td>Image picker</td>
	</tr>
	<tr>
		<td>Artikeltekst	</td>
		<td>Rich text Editor</td>
	</tr>
</table>


####SEO####

* På hvert kursus kan der administreres meta description og title. 
* Der kan endvidere defineres kursets canonical url.

![Kursus SEO](images/kursusseo.png)


<table>
	<tr>
	<th>Felt</th>
	<th>Felttype</th>
	</tr>
	<tr>
		<td>SEO</td>
		<td>Tab</td>
	</tr>
	<tr>
		<td>Meta Description</td>
		<td>Textfelt multi</td>
	</tr>
	<tr>
		<td>Title</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Caconical url</td>
		<td>Content picker</td>
	</tr>
</table>

####Kursus data####
* Felterne "Kviknummer", "Amu-pris" og "Pris udenfor målgruppe" importeres fra webservicen, og kan efterfølgende redigeres i Umbraco.  
* Feltet "Relaterede kurser" giver mulighed for at oprette en énvejs relation til relaterede kurser.  

![Kursus SEO](images/kursusdata.png)


<table>
	<tr>
		<th>Felt</th>
		<th>Felttype</th>
	</tr>
	<tr>
		<td>Kursus data</td>
		<td>Tab</td></tr>
	<tr>
		<td>Kursustype: IV-kursus, Amu, Ludus</td>
		<td>Radio button list</td>
	</tr>
	<tr>
		<td>Kviknummer</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Amu-pris</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Pris uden for målgruppe</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Relaterede kurser</td>
		<td>Related links datatype</td>
	</tr>
</table>

####Filer og links####

Relaterede filer og filer til download til alle AMU kurser kan defineres globalt, og kan overrides på det enkelte kursus. 
 
[![Hold](images/kursusfiler.png)](images/kursusfiler.png)



###Dokumenttype - "Hold"###
I niveauet under et givent kursus importeres x antal hold. 
Disse hold er defineret i webservice xml’en.  
Det er endvidere muligt manuelt at oprette hold under et kursus.

Et hold indeholder følgende felter:

[![Hold](images/hold.png)](images/hold.png)
	

<table>
	<tr>
		<th>Felt</th>
		<th>Felttype</th>
	</tr>
	<tr>
		<td>Hold</td>
		<td>Tab</td>
	</tr>
	<tr>
		<td>Holdnavn</td>
		<td>Nodens navn</td></tr>
	<tr>
		<td>Aflyst</td>
		<td>Checkfelt</td>
	</tr>
	<tr>
		<td>Skole</td>	
		<td>Dropdown</td>
	</tr>
	<tr>
		<td>Startdato</td>
		<td>Dato picker</td>
	</tr>
	<tr>
		<td>Slutdato</td>
		<td>Dato picker</td>
	</tr>
	<tr>
		<td>Tilmeldingsfrist	</td>
		<td>Dato picker</td>
	</tr>
	<tr>
		<td>Beskrivelse</td>
		<td>Textfelt multi</td>
	</tr>
	<tr>
		<td>Kontaktperson	</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Kontakt telefon	</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Udbudt antal pladser</td>
		<td>Textfelt</td>
	</tr>
	<tr>
		<td>Optaget antal pladser</td>
		<td>Textfelt</td>
	</tr>
</table>

Kursuspriserne beregnes ved import ud fra takstfil leveret fra ministeriet.  
Generelle relevante links kan defineres globalt, og overrides på det enkelte kursus.  


Frontend
--------
Ledige/optagede kurser skal indikeres bådes grafisk og med tekst “Ikke flere ledige pladser“ “ledige pladser“, “+10 ledige pladser”

Der oprettes mulighed for at finde kurset direkte ved søgning på Kviknummer, eks “280052k14ku33-40av“
Kviknummeret importeres fra Easy web servicen.

Det gøres muligt at administrere canonical på den enekelte side/kursus.
Det gøres muligt

Der tilrettes således, at der kan tilmeldes direkte via klik på kursusdatoen.

<!--
Design
=====

Forside
----------

Underside
-------------

UI elementer
---------

CMS
====

Dokumenttyper
------
### Forside ###
### Indholdsside ###
### Nyhed ###
### Person ###

Oprettelse af indhold
-------

Håndtering af billeder
--------
###Upload###
Billeder uploades til Umbraco vi drag and drop ind i upload feltet.  
Alternativt kan klikkes i upload feltet for at åbne en fil dialog.

[![upload billede](images/billedeupload.png)](images/billedeupload.png)


###Beskæring###

Håndtering af filer
--------

-->




