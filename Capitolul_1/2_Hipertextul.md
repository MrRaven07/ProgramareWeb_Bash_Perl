## 2. Hipertextul

---

### 2.1. 

Acest subcapitol prezintă o scurtă istorie a Hipertextului (Hypertext) precum și nevoia acestuia de a fi inventat.

> Hypertext is text displayed on a computer display or other electronic devices with references (hyperlinks) to other text that the reader can immediately access. Hypertext documents are interconnected by hyperlinks, which are typically activated by a mouse click, keypress set, or screen touch.
> 
> [Wikipedia: Hypertext](https://en.wikipedia.org/wiki/Hypertext)



<img width="50%" src="./cap1surse/Hyperlinks_scheme.svg.webp"/>

*Sursa: [Wikipedia Hyperlinks_scheme](https://en.wikipedia.org/wiki/File:Hyperlinks_scheme.svg)*

Imaginea de mai sus reprezintă conectarea dintre Hipertexte prin intermediul Hiperlinkurilor.

O colectie de "Hipertexte" poate fi reprezentată ca un graf orientat. 

Acest fapt imi aduce aminte de un proiect WebScraper mai vechi in care se incepe cu o pagina de start de unde se colecteaza toate *link-urile* (muchiile) și se vizitează urmatoarele noduri pe rand (dacă nu au fost vizitate deja).

Pentru a putea fi interpretate aceste Hipertexte, a fost folosită o interfață numită "browser", prin care "nodurile" (paginile) se puteau traversa.

> Nodul-sursă al unei legături se numește *referință*, iar cel destinație - *referent*. Nodurile conectate prin intermediul unei legături sunt denumite și *ancore*.(pag. 10)

În prezent se aude foarte des despre HTML (Hypertext Markup Language) ca limbaj de markup (și se spune destul de des că nu reprezintă un limbaj de programare propriu-zis), totodată există mai multe tipuri de astfel de limbaje de marcare:
- SGML (Standard Generalized Markup Language)
    - Necesită un DTD (Document Type Definition) pentru a declara ce etichete sunt permise și care este ierarhia lor
    - Status: Obsolet

Exemplu SGML:
```
<!DOCTYPE RAPORT [
<!ELEMENT RAPORT - - (TITLU, AUTOR, CONTINUT)>
<!ELEMENT TITLU - - (#PCDATA)>
<!ELEMENT AUTOR - - (#PCDATA)>
<!ELEMENT CONTINUT - - (#PCDATA)>
]>
<RAPORT>
  <TITLU>Analiza de Sistem</TITLU>
  <AUTOR>Departament IT</AUTOR>
  <CONTINUT>Verificarea parametrilor a fost finalizată cu succes.</CONTINUT>
</RAPORT>
```

- HTML (HyperText Markup Language)
    - Derivat inițial din SGML 
    - Spre deosebire de SGML (unde dezvoltatorul creează propriile etichete), HTML vine cu un vocabular predefinit și standardizat de etichete (tag-uri) pe care browserele web știu să le interpreteze (ex. `<h1>` pentru titluri, `<p>` pentru paragrafe).
  
Exemplu HTML:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Manual de Utilizare</title>
</head>
<body>
    <h1>Configurarea rețelei</h1>
    <p>Conectați cablul în portul marcat cu <strong>WAN</strong>.</p>
    <ul>
        <li>Pasul 1: Porniți routerul.</li>
        <li>Pasul 2: Așteptați semnalul luminos verde.</li>
    </ul>
</body>
</html>
```

- XML (eXtensible Markup Language)
    - Compromis între complexitatea extremă a SGML și rigiditatea HTML. Limbaj de marcare conceput exclusiv pentru stocarea și transportul datelor, nu pentru afișarea lor
    - Status: Destul de folosit, deși în dezvoltarea web modernă este înlocuit destul de mult de formatul JSON (JavaScript Object Notation)
    - Folosit în layout-urile aplicațiilor Android, configurări Java Spring și ca structură pentru alte formate de fișiere (ex. fișierele .docx din Microsoft Word sau grafica vectorială .svg care sunt teoretic fișiere XML arhivate).

Exemplu XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<inventar>
    <produs id="1042">
        <nume>Placă de bază</nume>
        <categorie>Componente Hardware</categorie>
        <pret_unitar moneda="EUR">150.00</pret_unitar>
        <in_stoc>true</in_stoc>
    </produs>
</inventar>
```

- MHEG (Multimedia and Hypermedia information coding Expert Group)
    - Diferit fata de cele prezentate, nu se bazeaza pe paranteze unghiulare `<>`, ci defineste clase si obiecte (abordare orientata pe obiecte) pentru a prezenta continut interactiv
    - Status: Obsolet

Exemplu MHEG:
```
{:Scene ( "Meniu_Principal" 0 )
  :Items (
    {:Rectangle fundalMeniu
      :OrigBoxSize 720 576
      :OrigPosition 0 0
      :OrigRefFillColour COLOUR_BLUE
    }
    {:Text txtTitlu
      :OrigContent "Apăsați butonul ROȘU pentru opțiuni"
      :OrigPosition 50 100
      :TextColour COLOUR_WHITE
    }
  )
}
```

- HyTime (Hypermedia/Time-based Structuring Language)
    - Construit ca extensie a limbajului SGML. Numele reflectă scopul principal de a adăuga dimensiuni de timp (Time) și spațiu pentru conținutul multimedia și crea legături (Hypermedia) complexe.
    - Status: Obsolet

Exemplu HyTime: 
```
<!-- Exemplu de legătură contextuală (clink) bidirecțională -->
<referinta HyTime="clink" linkend="capitolul_4">
  Vezi detalii în secțiunea de mentenanță.
</referinta>

<!-- Exemplu de sincronizare temporală (Eveniment) -->
<programare_evenimente HyTime="evsched">
  <eveniment_media id="sunet_avertizare" start="00:00:10" durata="00:00:05" HyTime="event">
    <audio fisier="alerta.wav"></audio>
  </eveniment_media>
</programare_evenimente>
```

> A markup language is a text-encoding system which specifies the structure and formatting of a document and potentially the relationships among its parts.[1] Markup can control the display of a document or enrich its content to facilitate automated processing.
>
> *[Sursa: Wikipedia Markup language](https://en.wikipedia.org/wiki/Markup_language)*




### 2.2.

În marcarea hipertextului se vorbește despre standardizarea reprezentării pe Web a documentelor prin HTML.

Totodată se exprimă posibilitatea ca HTML să fie înlocuit de XHTML. Nu am găsit nimic legat de acest gen căutând pe internet (dimpotrivă mai multe surse menționează că XHTML ar deveni obsolet). Pagina următoare de w3schools arată diferențe dintre XHTML și HTML https://www.w3schools.com/html/html_xhtml.asp .

Mai mult, HTML a trecut prin mai multe etape, HTML 2.0, HTML 3.2, HTML 4.0 (nu se menționeaza HTML5, intrucât a fost lansat în 2008).

Pentru dispozitive mobile de dimensiuni mici, HTML este înlocuit de:
- HDML (Handheld Device Markup Language)
    - Asemănător cu HTML, dar mult mai simplificat
    - Status: Obsolet

Exemplu de HDML:
```
<HDML VERSION=1.0>
  <!-- Prima carte din pachet (Afișare text și un buton de acțiune) -->
  <DISPLAY NAME="ecran_start">
    <ACTION TYPE=ACCEPT LABEL="Urmatorul" GO="#ecran_detalii">
    Bine ați venit în rețeaua mobilă!
  </DISPLAY>

  <!-- A doua carte din pachet -->
  <DISPLAY NAME="ecran_detalii">
    Semnalul este optim. Nu sunt mesaje noi.
  </DISPLAY>
</HDML>
```
- WML (Wireless Markup Language)
    - Evoluția standardizată a HDML. Creat de Wap Forum
    - Status: Obsolet

Exemplu de WML:
```
<?xml version="1.0"?>
<!DOCTYPE wml PUBLIC "-//WAPFORUM//DTD WML 1.1//EN" "http://www.wapforum.org/DTD/wml_1.1.xml">
<wml>
  <!-- Definirea primei cărți -->
  <card id="meniu" title="Portal WAP">
    <p>
      Știri de ultimă oră:<br/>
      <!-- Legătură către a doua carte din același pachet -->
      <a href="#vremea">Meteo</a><br/>
      <a href="http://exemplu.com/sport.wml">Sport</a>
    </p>
  </card>

  <!-- Definirea celei de-a doua cărți -->
  <card id="vremea" title="Vremea Azi">
    <p>
      București: 24 Grade Celsius, parțial înnorat.
    </p>
  </card>
</wml>
```

Prin rigiditate, se înțelege faptul că nu acceptă nicio eroare de sintaxă, dacă lipsește o singură paranteză programul refuză să fie citit și generează o eroare.   

Pentru a înfrumuseța afișarea informațiilor, au fost adăugate foile de stiluri în cascadă (CSS - Cascading Style Sheet), care se linkează cu fișierele HTML și permit schimbarea atributelor fiecărui tag în parte.

Exemplu CSS:
```css
selector {
    proprietate: valoare;
    proprietate: valoare;
}
```




