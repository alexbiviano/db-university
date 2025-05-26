# db-university

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.
Utilizzare https://www.drawio.com/ per la creazione dello schema. Esportare quindi il diagramma in jpg e caricarlo nella repo.
Buon lavoro!

26/05/2025

Dopo aver creato un nuovo database nel vostro MySQL Workbench e aver importato lo schema allegato, eseguite le query del file allegato.
Cosa consegnare?
Dopo aver testato le vostre query con MySQL Workbench, riportatele in un file txt e caricatelo nella vostra repo.

1. Selezionare tutti gli studenti nati nel 1990

SELECT \* FROM studenti WHERE YEAR(data_nascita) = 1990;

2. Selezionare tutti i corsi che valgono più di 10 crediti

SELECT name, cfu FROM courses WHERE (cfu) > 10;

3. Selezionare tutti gli studenti che hanno più di 30 anni

SELECT \* FROM studenti WHERE DATE_ADD(data_nascita, INTERVAL 30 YEAR) < CURDATE()

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea

SELECT name, period,year FROM courses WHERE period = 'I semestre' AND year = '1'

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

SELECT date, hour,course_id FROM exams WHERE date = '2020-06-20' AND hour >= '14:00:00'

6. Selezionare tutti i corsi di laurea magistrale

SELECT department_id, name,level FROM degrees WHERE level = 'magistrale'
