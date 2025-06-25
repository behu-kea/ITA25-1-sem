# Fullstack project

This portfolio project will be focused on creating the backend and frontend for a website. That means creating an API with endpoints that is connected to the database and using `fetch` in the frontend to get that data and display it



## Projects

You can either create your own website or choose one of the two projects we have described below. 



### ☕️ Hvilken cafe skal jeg studere i? 

Hjemmesiden skal kunne hjælpe folk med at finde en cafe at studere i



#### Problemet

Det er svært at finde den rigtige cafe at studere i. Nogle cafeer er små andre store, nogle er hyggelige, andre billige. Som bruger er det svært at finde det helt rigtige sted at studere

Fx kan det være man leder efter en cafe med wifi, hyggelig musik og god kaffe, eller måske vil man bare finde en cafe der er stille og med billig mad. 



#### Krav til backenden

- **Database**
  - Databasen skal understøtte at man som bruger kan favorite nogle cafeer. Derfor skal der skal være minimum 3 tabeller: `cafes`, `favorites` og `users`

- **API**
  - Der skal være et endpoint til hver entitet: `cafes` og `users` hvor alle entiteter bliver returneret
    - Fx `/cafes` returnerer alle cafeer i databasen
  - Der skal være et endpoint til hver entitet: `cafes` og `users` hvor en specifik entitet bliver returneret
    - Fx `/cafes/1` returnerer cafeen der har id 1
  - Man skal kunne filtrere cafeer med query parameters. 
    - Fx `/cafes?city=copenhagen` skal returnere et array af cafeer der ligger i `copenhagen`
  - Der skal være et endpoint hvor man opretter en ny cafe og en ny bruger
  
- **Krav til frontend**
  
  - Der skal være en liste af cafeer man kan se
  
  - Man skal på en måde kunne søge/filtrere/sortere cafeer så en bruger nemt kan finde en cafe at besøge der matcher deres behov



Hvilke attributter en cafe og en bruger skal have må i selv bestemme



I må meget gerne udvide funktionaliteten af backenden. Fx hvad hvis en bruger kunne favoritte en cafe. Måske kunne man tilføje pladser i cafeen osv. osv.



### 📸 Instagram spots

Denne verden er fyldt med utroligt flotte spots. Hvis man gerne vil finde flotte spots at tage billeder af til instagram, kan det være svært. Hvor skal man gå hen og hvor hvornår skal man være et sted. Det skal den her hjemmeside hjælpe med.

Et eksempel kunne være at man på hjemmesiden kan se at man skal tage til Bispebjerg Kirkegård i foråret når kirsebær træerne springer ud



#### Problemet

Som Instagram bruger vil man gerne tage flotte billeder, men hvor, hvornår og i hvilken retning præcis skal man tage dem?



#### Krav til backend

- **Database**
  - Databasen skal understøtte at man som bruger kan tilføje billeder. Derfor skal der være minimum 3 tabeller: `spots`, `images` og `users`

- **API**
  - Der skal være et endpoint til hver entitet: `spots`, `images` og `users` hvor alt bliver returneret. 
    - Fx `/spots` returnerer alle spots i databasen
  - Der skal være et endpoint til hver entitet: `spots`, `images` og `users` hvor en specifik entitet bliver returneret.  
    - Fx `/spots/1` returnerer det spot der har id 1
  - Man skal kunne filtrere spots med query parameters
    - Fx `/spots?season=winter`
  - Der skal være et endpoint hvor man opretter et nyt spot
  
- **Krav til frontend**
  
  - Man skal kunne se en liste af alle spots
  
  - Man skal kunne søge/filtrere/sortere så brugere nemt kan finde et spot at tage et billede



Hvilke attributter de forskellige entiteter skal have må i selv bestemme. Når i gemmer billeder skal i gemme url'en til hvor billedet ligger online!



I må meget gerne udvide funktionaliteten af backenden. Fx hvad hvis en bruger kunn favoritte et `spot` eller måske dele spots med andre brugere, hvordan ville det se ud på backenden?



### ✍️ Dit projekt her

Man må gerne lave sit eget projekt. Så længe der er en database, et api med minimum 2 endpoints og en frontend der henter data fra det api.



## Grupper



### Gruppe

1. Jeppe Susgaard Filsø
2. Alma Rebecca Castillo-Jørgense
3. Nicholas John Grønbech Ladik



### Gruppe

1. Mike Roland Johanson
2. Magnus August Giemsa
3. Andreas Østerskov Brandenborg



### Gruppe

1. Mathias Hjortkær Christensen
2. Frederikke Smærup Petersen
3. Esben Vittrup Dalegaard



### Gruppe

1. Nikoleta Greve Safarikas
2. Andreas Nørløv
3. Sahra Ali Weheliy Mohamud
4. Jonas Brøndum Hjelmblink



### Gruppe

1. Andreas Révész Gudmann
2. Christian Skovgaard Nielsen
3. Svetoslav Martinov Rasiyski



### Gruppe

1. Victor Lotz
2. Lukas Lind Kansakar
3. Johan Niemann Husbjerg



### Gruppe

1. Marc Victor Dahl Hendriksen
2. Nixhajete Jusufi



### Gruppe

1. Linea Moltved Skræp
2. Laurits Munk Hansen
3. Elias Benjamin Weiergang Garci



### Gruppe

1. Jacob Bisgaard
2. Felix Nørgaard Llambias
3. Faprao Raungsri



### Gruppe

- Victor Bischoff Mørkeberg
- Simon Junker Eriksen





## Afleveringer

Krav til aflevering

- Github link til backend repo
- Github link til frontend repo
- Sql fil i Github repositoriet



[Link fronteraflevering her](https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1322584) - **Skal aflevers inden d. 1/12 kl 23:59**



Fokus i opgaven er på koden. Hvis i får det deployet så flot. Hvis ikke, så gør det ikke noget. 
