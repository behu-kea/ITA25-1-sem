

# Data Quality, Cleaning & MySQL

**Preparation:**

- [Data Quality at A Glance](https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1154504)
- [SQL Update](https://www.mysqltutorial.org/mysql-update-data.aspx)
- [MySQL Delete](https://www.mysqltutorial.org/mysql-delete-statement.aspx)



## Peer instruction

#### What will the following query return?

```sql
SELECT *
FROM pokemon
WHERE special_defence > 50 AND `name` LIKE "%R"
```

**A)** All Pokemon with special defence above 50

**B)** All pokemon with special defence above 49 and a name ending with R

**C)** All pokemon with special defence above 50 and a name ending with R

**D** Invalid Query



### How many rows does the following query return?

```sql
SELECT *
FROM pokemon
WHERE secondary_type IS NULL
```

**A)** 0

**B)** 84

**C)** 151

**D** Invalid Query



### What will the following query return?

```sql
SELECT *
FROM pokemon
WHERE attack > defence OR primary_type = "fire" AND pokedex_number < 20
```

**A)** All pokemon where attack is higher than defence or all pokemon with the type "fire" and pokedex number is less than 20

**B)** All pokemon with a pokedex number less than twenty and either an attack higher than defence or primary type is fire 

**C)** All pokemon where attack is lower than defence, their primary type is fire and pokedex number less than 20

**D** Invalid Query





### Exercise 1: Par-øvelse

- **Observer følgende dataset**
  - https://sufoi.dk/obs/obs-2019/obs19-k3/
- **Besvar:**
  - Hvad er indholdet i datasettet? 
  - Hvilke kvalitetskriterier overskrider datasettet? 
  - Beskriv observationer og **hvordan** kvalitetskriterier overskrides
- **Udforsk:**
  - Hvordan er dataen indsamlet?
  - Hvem kan lave indberetninger? 
  - Er der en sammenhæng mellem indsamling og kvalitet?
- **Reflekter:**
  - Hvordan kan datakvaliteten hæves?



### Exercise 2: Par-øvelse

- **Opret en database og remove SAFE UPDATE**

```sql
CREATE DATABASE imdb;
use imdb;
SET SQL_SAFE_UPDATES = 0;
```

- **Data Exploration:**
  - Hvordan ser datasettet ud? Hvad beskriver det?
  
  - Identificer kolonner med NULL værdier?
  
  - Hvilke kolonner har problemer med fejlværdier (ifht. deres skala / "umulige" værdier - fx. en tidslængde mindre end 0)
  
    
  
- **Data Exploration & Data Cleaning**
  
  - Ret 3 **NULL** fejl i datasettet vha. UPDATE
  
  - Beskriv:
    - Hvordan fandt i fejlen?
    
    - Hvordan rettede i fejlen?
    
    - Hvordan perspektiverer det sig til jeres viden omkring data quality
    
      
  
- **Data Exploration & Data Cleaning**
  
  - Ret 3 **umulige** værdier () i datasettet vha. UPDATE
  - Beskriv:
    - Hvordan fandt i fejlen?
    - Hvordan rettede i fejlen?
    - Hvordan perspektiverer det sig til jeres viden omkring data quality
  
  

```SQL
DROP TABLE IF EXISTS imdb;
CREATE TABLE IF NOT EXISTS imdb(
   color                VARCHAR(16)
  ,director_name        VARCHAR(20)
  ,duration             INTEGER
  ,gross                INTEGER 
  ,genres               VARCHAR(40)
  ,movie_title          VARCHAR(43)
  ,title_year           INTEGER
  ,language             VARCHAR(7)
  ,country              VARCHAR(14)
  ,budget               VARCHAR(9)
  ,imdb_score           NUMERIC(4,1)
  ,actors               VARCHAR(56)
  ,movie_facebook_likes INTEGER
);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Martin Scorsese',240,116866727,'Biography|Comedy|Crime|Drama','The Wolf of Wall Street',2013,'English','USA','100000000',8.2,'Leonardo DiCaprio,Matthew McConaughey,Jon Favreau',138000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Shane Black',195,408992272,'Action|Adventure|Sci-Fi','Iron Man 3',2013,'English','USA','200000000',7.2,'Robert Downey Jr.,Jon Favreau,Don Cheadle',95000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('color','Quentin Tarantino',187,54116191,'Crime|Drama|Mystery|Thriller|Western','The Hateful Eight',2015,'English','USA','44000000',7.9,'Craig Stark,Jennifer Jason Leigh,Zoë Bell',114000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Kenneth Lonergan',186,46495,'Drama','Margaret',2011,'English','usa','14000000',6.5,'Matt Damon,Kieran Culkin,John Gallagher Jr.',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Peter Jackson',186,258355354,'Adventure|Fantasy','The Hobbit: The Desolation of Smaug',2013,'English','USA','225000000',7.9,'Aidan Turner,Adam Brown,James Nesbitt',83000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'N/A',183,330249062,'Action|Adventure|Sci-Fi','Batman v Superman: Dawn of Justice',202,'English','USA','250000000',6.9,'Henry Cavill,Lauren Cohan,Alan D. Purwin',197000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Peter Jackson',-50,303001229,'Adventure|Fantasy','The Hobbit: An Unexpected Journey',2012,'English','USA','180000000',7.9,'Aidan Turner,Adam Brown,James Nesbitt',166000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Edward Hall',180,NULL,'Drama|Romance','Restless',2012,'English','UK',NULL,7.2,'Rufus Sewell,Hayley Atwell,Charlotte Rampling',434);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Joss Whedon',173,623279547,'Action|Adventure|Sci-Fi','The Avengers',2012,'English','USA','220000000',8.1,'Chris Hemsworth,Robert Downey Jr.,Scarlett Johansson',123000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Joss Whedon',173,623279547,'Action|Adventure|Sci-Fi','The Avengers',2012,'English','USA','220000000',8.1,'Chris Hemsworth,Robert Downey Jr.,Scarlett Johansson',123000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Tom Tykwer',172,27098580,'Drama|Sci-Fi','Cloud Atlas',2012,'English','Germany','102000000',-7.5,'Tom Hanks,Jim Sturgess,Jim Broadbent',124000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,158,102515793,'Crime|Drama|Mystery|Thriller','The Girl with the Dragon Tattoo',2011,'English','USA','90000000',7.8,'Robin Wright,Goran Visnjic,Joely Richardson',54000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Christopher Spencer',170,59696176,NULL,'Son of God',2014,'English','USA','22000000',5.6,'Roma Downey,Amber Rose Revah,Darwin Shaw',15000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Christopher Nolan',169,187991439,'Adventure|Drama|Sci-Fi','Interstellar',2014,'English','USA','165000000',8.6,'Matthew McConaughey,Anne Hathaway,Mackenzie Foy',349000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','F. Gary Gray',167,161029270,'Biography|Crime|Drama|History|Music','Straight Outta Compton',2015,'English','USA','28000000',7.9,'Aldis Hodge,Neil Brown Jr.,R. Marcos Taylor',76000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Richard Linklater',165,25359200,'Drama','Boyhood',2014,'English','USA','4000000',8,'Ellar Coltrane,Lorelei Linklater,Libby Villari',92000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Quentin Tarantino',580,162804648,'Drama|Western','Django Unchained',2012,'English','USA','100000000',8.5,'Leonardo DiCaprio,Christoph Waltz,Ato Essandoh',199000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Michael Bay',165,245428137,'Action|Adventure|Sci-Fi','Transformers: Age of Extinction',2014,'English','USA','210000000',5.7,'Bingbing Li,Sophia Myles,Kelsey Grammer',56000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Christopher Nolan',164,448130642,'Action|Thriller','The Dark Knight Rises',2012,'English','USA','250000000',8.5,'Tom Hardy,Christian Bale,Joseph Gordon-Levitt',164000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Peter Jackson',164,255108370,'Adventure|Fantasy','The Hobbit: The Battle of the Five Armies',2014,'English','New Zealand','250000000',7.5,'Aidan Turner,Adam Brown,James Nesbitt',65000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Tom Hooper',158,148775460,'Drama|Musical|Romance','Les Misérables',2012,'English','USA','61000000',7.6,'Hugh Jackman,Eddie Redmayne,Anne Hathaway',144000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Tom Hooper',158,148775460,'Drama|Musical|Romance','Les Misérables',2012,'English','USA','61000000',7.6,'Hugh Jackman,Eddie Redmayne,Anne Hathaway',144000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Kathryn Bigelow',157,95720716,'Drama|History|Thriller','Zero Dark Thirty',2012,'English','USA','40000000',7.4,'Jennifer Ehle,Harold Perrineau,Parker Sawyers',39000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Ridley Scott',156,105219735,'Action|Adventure|Drama|History','Robin Hood',2010,'English','USA','200000000',6.7,'Mark Addy,William Hurt,Scott Grimes',17000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,156,183635922,'Adventure|Drama|Thriller|Western','The Revenant',2015,'English','USA','135000000',8.1,'Leonardo DiCaprio,Tom Hardy,Lukas Haas',190000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Michael Bay',154,352358779,'Action|Adventure|Sci-Fi','Transformers: Dark of the Moon',2011,'English','USA','195000000',6.3,'Glenn Morshower,Lester Speight,Kevin Dunn',46000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Denis Villeneuve',153,60962878,'Crime|Drama|Mystery|Thriller','Prisoners',2013,'English','USA','46000000',8.1,'Hugh Jackman,Jake Gyllenhaal,Dylan Minnette',86000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Gnana Rajasekaran',153,NULL,'Biography|Drama|History','Ramanujan',2014,'English','India',NULL,7,'Mani Bharathi,Michael Lieber,Kevin McGowan',58);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Marc Webb',153,262030663,'Action|Adventure|Fantasy','The Amazing Spider-Man',2012,'English','USA','230000000',7,'Emma Stone,Andrew Garfield,Chris Zylka',56000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Nan',151,228430993,'Adventure|Drama|Sci-Fi','The Martian',2015,'English','USA','108000000',8.1,'Matt Damon,Donald Glover,Benedict Wong',153000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Ridley Scott',150,65007045,'Action|Adventure|Drama','Exodus: Gods and Kings',2014,'English','UK','140000000',6.1,'Christian Bale,María Valverde,Ben Mendelsohn',51000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Ridley Scott',150,65007045,'Action|Adventure|Drama','Exodus: Gods and Kings',2014,'English','UK','140000000',6.1,'Christian Bale,María Valverde,Ben Mendelsohn',51000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,150,182204440,'Biography|Drama|History|War','Lincoln',2012,'English','USA','65000000',7.4,'Joseph Gordon-Levitt,Hal Holbrook,Bruce McGill',71000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Mike Leigh',150,3958500,'Biography|Drama|History','Mr. Turner',2014,'English','UK','N/A',6.8,'Lesley Manville,Ruth Sheen,Karl Johnson',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Gore Verbinski',650,89289910,'Action|Adventure|Western','The Lone Ranger',2013,'English','USA','215000000',6.5,'Johnny Depp,Ruth Wilson,Tom Wilkinson',48000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','David Fincher',149,167735396,'Crime|Drama|Mystery|Thriller','Gone Girl',2014,'English','USA','61000000',8.1,'Patrick Fugit,Sela Ward,Emily Ratajkowski',146000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Bryan Singer',149,233914986,'Action|Adventure|Fantasy|Sci-Fi|Thriller','X-Men: Days of Future Past',2014,'English','United States','200000000',8,'Jennifer Lawrence,Peter Dinklage,Hugh Jackman',82000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Jay Oliva',148,NULL,'Action|Animation|Crime|Sci-Fi|Thriller','Batman: The Dark Knight Returns, Part 2',2013,'English','USA','3500000',8.4,'Michael Emerson,Mark Valley,Grey Griffin',5000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Christopher Nolan',148,292568851,'Action|Adventure|Sci-Fi|Thriller','Inception',2010,'English','USA','160000000',8.8,'Leonardo DiCaprio,Tom Hardy,Joseph Gordon-Levitt',175000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Paul Thomas Anderson',148,8093318,'Comedy|Crime|Drama|Mystery|Romance','Inherent Vice',2014,'English','USA','20000000',6.7,'Martin Dew,Katherine Waterston,Serena Scott Thomas',18000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Sam Mendes',148,200074175,'Action|Adventure|Thriller','Spectre',2015,'English','UK','245000000',6.8,'Christoph Waltz,Rory Kinnear,Stephanie Sigman',85000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,147,407197282,'Action|Adventure|Sci-Fi','Captain America: Civil War',2016,'English','USA','250000000',8.2,'Robert Downey Jr.,Scarlett Johansson,Chris Evans',72000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Michael Patrick King',146,95328937,'Comedy|Drama|Romance','Sex and the City 2',2010,'English','USA','100000000',4.3,'Chris Noth,Liza Minnelli,Kristin Davis',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Tate Taylor',146,169705587,'Drama','The Help',2011,'English','USA','25000000',8.1,'Emma Stone,Bryce Dallas Howard,Mike Vogel',75000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Francis Lawrence',146,424645577,'Adventure|Sci-Fi|Thriller','The Hunger Games: Catching Fire',2013,'English','USA','130000000',7.6,'Jennifer Lawrence,Josh Hutcherson,Sandra Ellis Lafferty',82000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Black and White','Steven Spielberg',146,79883359,'Drama|War','War Horse',2011,'English','usa','66000000',7.2,'Jeremy Irvine,Benedict Cumberbatch,Eddie Marsan',28000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Michael Bay',144,52822418,'Action|Drama|Thriller|War','13 Hours',2016,'English','USA','50000000',7.4,'Toby Stephens,James Badge Dale,David Costabile',44000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Guillaume Canet',144,41229,'Crime|Drama|Thriller','Blood Ties',2013,'English','France','25500000',6.5,'Mila Kunis,Lili Taylor,Billy Crudup',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Paul Thomas Anderson',144,16377274,'Drama','The Master',2012,'English','USA','32000000',7.1,'Mike Howard,Jeffrey W. Jenkins,Bruce Goodchild',27000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Bryan Singer',144,154985087,'Action|Adventure|Sci-Fi','X-Men: Apocalypse',2016,'English','USA','178000000',7.3,'Jennifer Lawrence,Michael Fassbender,Tye Sheridan',54000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Adam McKay',143,2175312,'Comedy','Anchorman 2: The Legend Continues',2013,'English','USA','50000000',6.3,'Harrison Ford,Will Ferrell,Steve Carell',41000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Zack Snyder',143,291021565,'Action|Adventure|Fantasy|Sci-Fi','Man of Steel',2013,'English','USA','225000000',7.2,'Henry Cavill,Christopher Meloni,Harry Lennix',118000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Sam Mendes',143,304360277,'Action|Adventure|Thriller','Skyfall',2012,'English','UK','200000000',7.8,'Albert Finney,Helen McCrory,Rory Kinnear',80000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Sam Mendes',143,304360277,'Action|Adventure|Thriller','Skyfall',2012,'English','UK','200000000',7.8,'Albert Finney,Helen McCrory,Rory Kinnear',80000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Baz Luhrmann',143,144812796,'Drama|Romance','The Great Gatsby',2013,'English','Australia','105000000',7.3,'Leonardo DiCaprio,Elizabeth Debicki,Steve Bisley',115000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Baz Luhrmann',143,144812796,'Drama|Romance','The Great Gatsby',2013,'English','Australia','105000000',7.3,'Leonardo DiCaprio,Elizabeth Debicki,Steve Bisley',115000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,NULL,143,NULL,'Drama|Horror|Thriller','The Ridges',2011,'English','USA','17350',3,'Robbie Barnes,Alana Kaniewski,Brandon Landers',33);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Steven Spielberg',142,72306065,'Drama|History|Thriller','Bridge of Spies',2015,'English','USA','40000000',7.6,'Tom Hanks,Mark Rylance,Amy Ryan',55000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Marc Webb',142,202853933,'Action|Adventure|Fantasy|Sci-Fi','The Amazing Spider-Man 2',2014,'English','USA','200000000',6.7,'Emma Stone,Andrew Garfield,B.J. Novak',41000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,142,407999255,'Adventure|Drama|Sci-Fi|Thriller','The Hunger Games',2012,'English','USA','78000000',7.3,'Jennifer Lawrence,Josh Hutcherson,Anthony Reynolds',140000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Joss Whedon',141,458991599,'Action|Adventure|Sci-Fi','Avengers: Age of Ultron',2015,'English','USA','250000000',7.5,'Chris Hemsworth,Robert Downey Jr.,Scarlett Johansson',118000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Timur Bekmambetov',141,NULL,'Adventure|Drama|History','Ben-Hur',2016,'English','USA','100000000',6.1,'Morgan Freeman,Ayelet Zurer,Moises Arias',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Timur Bekmambetov',141,NULL,'Adventure|Drama|History','Ben-Hur',2016,'English','USA','100000000',6,'Morgan Freeman,Ayelet Zurer,Moises Arias',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Timur Bekmambetov',141,NULL,'Adventure|Drama|History','Ben-Hur',2016,'English','USA','100000000',6.1,'Morgan Freeman,Ayelet Zurer,Moises Arias',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Justin Chadwick',141,8324748,'Biography|Drama|History','Mandela: Long Walk to Freedom',2013,'English','UK','35000000',7.1,'Terry Pheto,Fana Mokoena,Tony Kgoroge',13000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Oliver Stone',141,47307550,'Crime|Drama|Thriller','Savages',2012,'English','USA','45000000',6.5,'Demián Bichir,Shea Whigham,Gary Stretch',28000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','David Dobkin',141,47105085,'Crime|Drama','The Judge',2014,'English','USA','50000000',7.4,'Robert Downey Jr.,Robert Duvall,Leighton Meester',47000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Ryan Murphy',140,80574010,'Drama|Romance','Eat Pray Love',2010,'English','USA','60000000',5.7,'James Franco,Julia Roberts,Billy Crudup',26000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','James Wan',140,350034110,'Action|Crime|Thriller','Furious 7',2015,'English','USA','190000000',7.2,'Jason Statham,Paul Walker,Vin Diesel',94000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Derek Cianfrance',140,21383298,'Crime|Drama|Thriller','The Place Beyond the Pines',2012,'English','USA','15000000',7.3,'Ryan Gosling,Ben Mendelsohn,Angelo Anthony Pizza',47000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Gavin O''Connor',140,13651662,'Drama|Sport','Warrior',2011,'English','USA','25000000',8.2,'Tom Hardy,Frank Grillo,Kevin Dunn',77000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,139,150832203,'Adventure|Mystery|Sci-Fi','Divergent',2014,'English','USA','85000000',6.7,'Kate Winslet,Theo James,Mekhi Phifer',49000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Gary Ross',139,20389967,'Action|Biography|Drama|History|War','Free State of Jones',2016,'English','USA','50000000',6.7,'Matthew McConaughey,Donald Watkins,Jessica Collins',10000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Tate Taylor',139,30513940,'Biography|Drama|Music','Get on Up',2014,'English','USA','30000000',6.9,'Tika Sumpter,Josh Hopkins,Aunjanue Ellis',11000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Terrence Malick',139,13303319,'Drama|Fantasy','The Tree of Life',2011,'English','USA','32000000',6.7,'Brad Pitt,Tye Sheridan,Fiona Shaw',39000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,138,150117807,'Crime|Drama','American Hustle',2013,'English','USA','40000000',7.3,'Jennifer Lawrence,Christian Bale,Bradley Cooper',63000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Robert Zemeckis',138,93749203,'Drama|Thriller','Flight',2012,'English','USA','31000000',7.3,'Denzel Washington,Bruce Greenwood,Nadine Velazquez',64000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Darren Aronofsky',138,101160529,'Action|Adventure|Drama','Noah',2014,'English','USA','125000000',5.8,'Anthony Hopkins,Emma Watson,Logan Lerman',71000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Martin Scorsese',138,127968405,'Mystery|Thriller','Shutter Island',2010,'English','USA','80000000',8.1,'Leonardo DiCaprio,Joseph Sikora,Nellie Sciutto',53000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Ridley Scott',138,16969390,'Crime|Drama|Thriller','The Counselor',2013,'English','USA','25000000',5.3,'Michael Fassbender,Brad Pitt,Goran Visnjic',24000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'James Mangold',138,132550960,'Action|Adventure|Sci-Fi|Thriller','The Wolverine',2013,'English','USA','120000000',6.7,'Hugh Jackman,Tao Okamoto,Rila Fukushima',68000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Daniel Espinosa',137,1206135,'Crime|Drama|Thriller','Child 44',205,'English','Czech Republic','50000000',6.4,'Tom Hardy,Fares Fares,Michael Nardone',18000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,137,37304950,'Biography|Crime|Drama','J. Edgar',2011,'English','USA','35000000',6.6,'Leonardo DiCaprio,Naomi Watts,Kaitlyn Dever',16000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Walter Salles',137,717753,'Adventure|Drama','On the Road',2012,'English','France','25000000',6.1,'Kristen Stewart,Viggo Mortensen,Kirsten Dunst',27000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,137,281666058,'Adventure|Sci-Fi','The Hunger Games: Mockingjay - Part 2',2015,'English','USA','160000000',6.6,'Jennifer Lawrence,Philip Seymour Hoffman,Josh Hutcherson',38000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Angelina Jolie Pitt',137,115603980,'Biography|Drama|Sport|War','Unbroken',2014,'English','USA','65000000',-1.2,'Finn Wittrock,Jack O''Connell,Alex Russell',35000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Angelina Jolie Pitt',137,115603980,'Biography|Drama|Sport|War','Unbroken',2014,'English','USA','65000000',7.2,'Finn Wittrock,Jack O''Connell,Alex Russell',35000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES (NULL,'Seth MacFarlane',136,42615685,'Comedy|Western','A Million Ways to Die in the West',2014,'English','USA','40000000',6.1,'Liam Neeson,Charlize Theron,Seth MacFarlane',24000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Anthony Russo',136,259746958,'Action|Adventure|Sci-Fi','Captain America: The Winter Soldier',2014,'English','usa','170000000',7.8,'Scarlett Johansson,Chris Evans,Hayley Atwell',55000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Rob Marshall',136,241063875,'Action|Adventure|Fantasy','Pirates of the Caribbean: On Stranger Tides',2011,'English','USA','250000000',6.7,'Johnny Depp,Sam Claflin,Stephen Graham',58000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Adam Shankman',136,38509342,'Comedy|Drama|Musical|Romance','Rock of Ages',2012,'English','USA','75000000',5.9,'James Martin Kelly,Shane Hartline,Celina Beach',33000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color',NULL,136,52474616,'Drama','Wall Street: Money Never Sleeps',2010,'English','USA','70000000',6.3,'Frank Langella,Austin Pendleton,John Buffalo Mailer',13000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Sadyk Sher-Niyaz',135,NULL,'Action|Biography|Drama|History','Queen of the Mountains',2014,'English','Kyrgyzstan','1400000',8.7,'Elina Abai Kyzy,Aziz Muradillayev,Mirlan Abdulayev',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Tony Gilroy',135,113165635,'Action|Adventure|Thriller','The Bourne Legacy',2012,'English','USA','125000000',6.7,'Jeremy Renner,Scott Glenn,Stacy Keach',31000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Steve McQueen',134,56667870,'Biography|Drama|History','12 Years a Slave',2013,'English','USA','20000000',8.1,'Quvenzhané Wallis,Scoot McNairy,Taran Killam',83000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Richard J. Lewis',134,7501404,'Comedy|Drama','Barney''s Version',2010,'English','Canada',NULL,7.3,'Mark Addy,Atom Egoyan,Paul Gross',0);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Paul Greengrass',134,107100855,'Biography|Drama|Thriller','Captain Phillips',2013,'English','USA','55000000',7.9,'Tom Hanks,Chris Mulkey,Michael Chernus',65000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','David Ayer',134,85707116,'Action|Drama|War','Fury',2014,'English','USA','68000000',7.6,'Brad Pitt,Logan Lerman,Jim Parrack',82000);
INSERT INTO imdb(color,director_name,duration,gross,genres,movie_title,title_year,language,country,budget,imdb_score,actors,movie_facebook_likes) VALUES ('Color','Clint Eastwood',5,47034272,'Biography|Drama|Music|Musical','Jersey Boys',2014,'English','USA','40000000',6.9,'Johnny Cannizzaro,Steve Schirripa,Scott Vance',16000);

```

