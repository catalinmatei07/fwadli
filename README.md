# fwadli
lucrare individuala

UNIVERSITATEA DE STAT DIN MOLDOVA

FACULTATEA  MATEMATICĂ ŞI INFORMATICĂ DEPARTAMENTUL INFORMATICĂ



Matei Catalin IAFR2101



Lucrare individuala
la disciplina Framework-uri Pentru Dezvoltarea Web



Chişinău,  2024




Introducere
În cadrul acestui proiect, am dezvoltat o aplicație de gestionare a filmelor, folosind framework-ul Node.js și librăria Express pentru partea de server. Aplicația permite utilizatorilor să vizualizeze, adauge, editeze și șteargă filme, gestionând datele acestora într-un fișier JSON. De asemenea, am implementat funcționalități de bază pentru interacțiunea cu utilizatorii, oferind o interfață simplă și intuitivă.



Frameworkuri
Pentru dezvoltarea aplicației, am utilizat următoarele framework-uri:
•	Node.js: Un runtime JavaScript care permite rularea codului JavaScript pe server, ideal pentru aplicații web scalabile.
•	Express.js: Un framework minimal și flexibil pentru Node.js care facilitează dezvoltarea aplicațiilor web și a API-urilor, oferind funcționalități pentru gestionarea rutelor, manipularea cererilor HTTP și integrarea ușoară cu fișierele statice.
Tool-uri utilizate
•	MySQL – pentru stocarea datelor aplicației.
•	Sequelize – pentru gestionarea interacțiunii cu MySQL printr-un ORM.
•	Postman – pentru testarea API-ului.


 



Dezvoltarea părții client a aplicației


Partea client a aplicației este esențială pentru experiența utilizatorului, deoarece este interfața cu care utilizatorii interacționează direct. Scopul acestei secțiuni este de a crea o aplicație web intuitivă și ușor de utilizat, care să permită utilizatorilor să vizualizeze filme, să adauge filme noi, să le editeze și să le șteargă. Partea client se conectează la backend-ul aplicației printr-un API RESTful, realizând toate operațiile necesare pe baza datelor disponibile. În plus, aplicația oferă funcționalități suplimentare, cum ar fi căutarea și filtrarea filmelor, pentru a îmbunătăți experiența utilizatorului.

Crearea interfeței utilizator
1.	Structura HTML
Pentru partea client, structura aplicației este construită folosind HTML. Aceasta definește principalele elemente de interfață ale aplicației, cum ar fi listele de filme, formularele de adăugare, editare și ștergere, precum și butoanele de interacțiune (de exemplu, butoanele de "Vizualizare" și "Ștergere"). Elementele HTML definesc locațiile unde sunt afișate filmele și alte informații relevante, cum ar fi titlurile, descrierile și imaginile acestora. De asemenea, HTML-ul permite crearea unor formulare care permit utilizatorilor să adauge sau să editeze filmele existente.
2.	Stilizarea cu CSS
CSS (Cascading Style Sheets) este utilizat pentru a stiliza paginile web și a le face mai atractive din punct de vedere vizual. Aplicarea unui design responsive și adaptabil, care să se regăsească pe diferite dispozitive (desktop, tabletă, mobil), este esențială pentru îmbunătățirea experienței utilizatorului. În cadrul aplicației, CSS-ul este folosit pentru a organiza elementele pe pagină, a defini culori, fonturi și margini, și a crea efecte vizuale (de exemplu, shadowing, hover effects).
 

3.	Funcționalități JavaScript
JavaScript este folosit pentru a adăuga interactivitate aplicației. Acesta permite interacțiunea cu utilizatorul, gestionarea evenimentelor și manipularea dinamică a conținutului paginii. De exemplu, când utilizatorul apasă pe un buton pentru a vizualiza detaliile unui film, JavaScript va trimite o cerere către server pentru a obține informațiile suplimentare despre filmul respectiv și le va afișa pe pagină, fără a reîncărca întreaga pagină.
Printre funcționalitățile cheie implementate în partea client se numără:
o	Vizualizarea filmelor: Filtrarea și afișarea filmelor din baza de date pe pagină. Fiecare film va avea o imagine reprezentativă, un titlu și, eventual, un scurt rezumat.
o	Adăugarea unui film: Un formular care permite utilizatorilor să adauge filme noi în aplicație. Aceasta presupune completarea unui formular cu informații precum titlul, genul, anul lansării, descrierea și imaginea filmului. La trimiterea formularului, aceste informații sunt trimise către server pentru a fi stocate în baza de date.
o	Ștergerea unui film: O opțiune prin care utilizatorii pot elimina un film din listă. Aceasta presupune un buton "Șterge" asociat fiecărui film, iar printr-un click, filmul respectiv este eliminat din baza de date.
o	Vizualizarea detaliilor unui film: La selectarea unui film, utilizatorul va putea vizualiza detalii suplimentare despre acel film, cum ar fi descrierea completă, anul lansării și orice alte informații relevante.
4.	Interacțiunea cu API-ul backend
Partea client a aplicației interacționează cu partea backend prin intermediul unui API (Application Programming Interface). Acest API permite partea client să comunice cu serverul pentru a obține informații despre filme, a adăuga, edita sau șterge filmele din baza de date.
API-ul backend va expune diferite endpointuri care permit următoarele operații:
o	GET /movies: Obține lista completă a filmelor din baza de date.
o	POST /movies: Adaugă un film nou în baza de date.
o	DELETE /movies/{id}: Șterge un film pe baza identificatorului său unic.
o	PUT /movies/{id}: Actualizează informațiile unui film existent.
Aceste operații sunt realizate prin cereri HTTP (de exemplu, GET, POST, DELETE, PUT), iar partea client va trimite aceste cereri folosind JavaScript, de obicei cu ajutorul tehnologiilor fetch sau axios. Răspunsurile primite de la server (de obicei, în format JSON) vor fi procesate și utilizate pentru a actualiza interfața utilizatorului.
5.	Validarea datelor la client
Este esențial ca datele trimise de utilizatori prin intermediul formularelor să fie validate corect înainte de a fi trimise la server. Acest proces de validare ajută la prevenirea erorilor și a datelor incorecte. Validarea la client poate include verificarea faptului că toate câmpurile sunt completate corect (de exemplu, câmpurile obligatorii nu sunt lăsate goale), că datele sunt în formatul corect (de exemplu, anul filmului este un număr valid) și că imaginea are un URL valid.
Validarea la client se poate face cu ajutorul JavaScript-ului, iar dacă datele nu sunt valide, utilizatorului îi va fi prezentat un mesaj de eroare înainte ca formularul să fie trimis către server.
 

6.	Funcționalități suplimentare
În plus față de funcțiile de bază (vizualizare, adăugare, ștergere), aplicația poate include funcționalități suplimentare pentru a îmbunătăți experiența utilizatorului, cum ar fi:
o	Căutare și filtrare: Utilizatorii pot căuta filme după titlu sau filtra filmele pe baza unor criterii precum genul sau anul lansării.
o	Sortare: Permite utilizatorilor să sorteze lista de filme după diferite criterii, cum ar fi titlul sau anul.
o	Design responsiv: Aplicația este optimizată pentru a funcționa pe diverse dispozitive, inclusiv desktop, tablete și telefoane mobile. Acest lucru este realizat prin utilizarea tehnicilor de design responsive, care ajustează elementele paginii în funcție de dimensiunea ecranului.
7.	Gestionarea erorilor
Partea client a aplicației trebuie să gestioneze corespunzător erorile care pot apărea în timpul interacțiunii cu API-ul backend. De exemplu, dacă o cerere către server eșuează din cauza unei conexiuni slabe sau a unei erori interne pe server, utilizatorul va fi informat printr-un mesaj de eroare prietenos, care să explice problema și să sugereze acțiuni corective (de exemplu, "A apărut o problemă la server. Vă rugăm să încercați din nou mai târziu.").
 
 
![image](https://github.com/user-attachments/assets/84d9e62d-6732-41d4-b57d-bed71dc8b1ae)

 ![image](https://github.com/user-attachments/assets/5f0a284b-3afc-44ae-94e6-9beb1367709f)


 

 


 

Dezvoltarea părții server a aplicației
Cerințe funcționale
Backend-ul aplicației trebuia să ofere un API care să interacționeze cu baza de date pentru a oferi funcționalitățile CRUD (Creare, Citire, Actualizare, Ștergere) pentru filme. Aceste operațiuni sunt esențiale pentru gestionarea filmelor, iar datele sunt stocate într-o bază de date MySQL. De asemenea, este necesar să implementăm un sistem de autentificare și autorizare a utilizatorilor pentru a proteja resursele sensibile.
Dezvoltarea backend-ului
1.	Crearea unui server cu Node.js și Express.js
În prima etapă, am instalat Node.js și am creat un server simplu folosind Express.js. Iată un exemplu de cod pentru inițializarea serverului:

const express = require('express');
const app = express();
const port = 3000;

app.use(express.json());

app.get('/', (req, res) => {
    res.send('Bine ai venit la API-ul Cinema!');
});

app.listen(port, () => {
    console.log(`Serverul rulează pe http://localhost:${port}`);
});
 

2.	Configurarea bazei de date MySQL
Utilizând Sequelize, un ORM pentru MySQL, am creat modelele pentru filme și utilizatori. Modelul pentru filme ar putea arăta astfel:

const { Sequelize, DataTypes } = require('sequelize');
const sequelize = new Sequelize('cinema_db', 'root', 'password', {
    host: 'localhost',
    dialect: 'mysql'
});

const Movie = sequelize.define('Movie', {
    title: {
        type: DataTypes.STRING,
        allowNull: false
    },
    genre: {
        type: DataTypes.STRING,
        allowNull: false
    },
    year: {
        type: DataTypes.INTEGER,
        allowNull: false
    },
    description: {
        type: DataTypes.TEXT,
        allowNull: true
    },
    image: {
        type: DataTypes.STRING,
        allowNull: true
    }
});

sequelize.sync().then(() => {
    console.log('Baza de date a fost sincronizată cu succes');
});
 
3.	Rute API pentru gestionarea filmelor
Am creat rute API pentru gestionarea filmelor, utilizând metodele CRUD. Iată cum ar putea arăta rutele pentru adăugarea, obținerea și ștergerea filmelor:
•	Creare film:
app.post('/movies', async (req, res) => {
    try {
        const { title, genre, year, description, image } = req.body;
        const movie = await Movie.create({
            title,
            genre,
            year,
            description,
            image
        });
        res.status(201).json(movie);
    } catch (error) {
        res.status(400).json({ error: 'A apărut o eroare la adăugarea filmului.' });
    }
});

Obținerea tuturor filmelor:
app.get('/movies', async (req, res) => {
    try {
        const movies = await Movie.findAll();
        res.status(200).json(movies);
    } catch (error) {
        res.status(400).json({ error: 'A apărut o eroare la obținerea filmelor.' });
    }
});
 
Sergerea unui film

app.delete('/movies/:id', async (req, res) => {
    try {
        const movie = await Movie.findByPk(req.params.id);
        if (movie) {
            await movie.destroy();
            res.status(200).json({ message: 'Filmul a fost șters cu succes.' });
        } else {
            res.status(404).json({ error: 'Filmul nu a fost găsit.' });
        }
    } catch (error) {
        res.status(400).json({ error: 'A apărut o eroare la ștergerea filmului.' });
    }
});

4.	  Autentificare și autorizare
Pentru a adăuga un sistem de autentificare și autorizare, am implementat JWT (JSON Web Tokens). Iată un exemplu de implementare a autentificării:
	Autentificarea utilizatorilor:
const jwt = require('jsonwebtoken');

app.post('/login', async (req, res) => {
    const { username, password } = req.body;

  Verificarea credențialelor utilizatorului
    const user = await User.findOne({ where: { username } });
    if (!user || user.password !== password) {
        return res.status(401).json({ error: 'Credențiale invalide.' });
    }

   Generarea token-ului JWT
    const token = jwt.sign({ id: user.id, username: user.username }, 'secretKey', { expiresIn: '1h' });
    res.json({ token });
});
Protejarea rutelor cu JWT:
const authenticate = (req, res, next) => {
    const token = req.headers['authorization'];
    if (!token) return res.status(403).json({ error: 'Acces interzis.' });

  jwt.verify(token, 'secretKey', (err, decoded) => {
        if (err) return res.status(403).json({ error: 'Token invalid.' });
        req.user = decoded;
        next();
    });
};

app.post('/movies', authenticate, async (req, res) => {
    // Crearea filmului (numai utilizatorii autentificați pot adăuga filme)
});
5.	Validarea datelor
Validarea datelor pentru cererile de la client este esențială pentru a asigura integritatea datelor din baza de date. Folosind Joi, o librărie de validare, am validat datele pentru a preveni inserarea de date incorecte:
const Joi = require('joi');

const movieSchema = Joi.object({
    title: Joi.string().required(),
    genre: Joi.string().valid('act', 'com', 'drama').required(),
    year: Joi.number().integer().min(1900).max(2100).required(),
    description: Joi.string().optional(),
    image: Joi.string().uri().optional()
});

app.post('/movies', async (req, res) => {
    const { error } = movieSchema.validate(req.body);
    if (error) return res.status(400).json({ error: error.details[0].message });


});


 
Concluzie

În cadrul acestui proiect, am dezvoltat o aplicație web pentru gestionarea unui catalog de filme, utilizând atât tehnologiile de frontend, cât și de backend, pentru a crea o soluție funcțională și intuitivă. Am ales să implementăm un design simplu și eficient, care să permită utilizatorilor să adauge, vizualizeze, editeze și șteargă filme, folosind o interfață accesibilă și ușor de utilizat.
Deși, din motive tehnice, aplicația nu a fost conectată la o bază de date reală, am explicat teoretic cum ar fi fost structurat backend-ul pentru a permite un sistem CRUD complet, cu validarea datelor și gestionarea erorilor corespunzătoare. În plus, partea client a fost proiectată pentru a oferi o experiență fluidă, cu funcționalități de căutare, filtrare și validare a datelor.
Acest proiect a demonstrat importanța utilizării framework-urilor moderne și a tehnologiilor web pentru dezvoltarea aplicațiilor, fiind un exemplu de cum pot fi integrate diverse componente pentru a crea o aplicație completă și eficientă. Chiar dacă nu am implementat toate componentele planificate, am reușit să creăm un prototip funcțional care poate fi extins în viitor, având în vedere implementarea unei baze de date și a unui sistem de autentificare și autorizare.
În concluzie, acest proiect a fost o bună oportunitate de a învăța și aplica cunoștințe de dezvoltare web, precum și de a înțelege fluxul de date între frontend și backend într-o aplicație reală.

