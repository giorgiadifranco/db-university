# db-university

Modellare la struttura di un database per memorizzare tutti i dati riguardanti una università:

1. sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
2. ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
3. ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
4. ogni Corso può essere tenuto da diversi Insegnanti;
5. ogni Corso prevede più appelli d'Esame;
6. ogni Studente è iscritto ad un solo Corso di Laurea;
7. ogni Studente può iscriversi a più appelli di Esame;
8. per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.

Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## tables name:

- departments
- degree programme
- courses of study
- teachers
- exams
- exam sessions
- students

## departement: table structure

- id | BIGINT -AUTO_INCREMENT - PRIMARY_KEY (UNIQUE, NOTNULL)
- name | varchar (20) - not null
- head_of_department
- website
- description
- email_address

## degree programme: table structure

- id | BIGINT -AUTO_INCREMENT - PRIMARY_KEY (UNIQUE, NOTNULL)
- name | varchar (20) - not null
- descrption | text
- id_department

## course_of_study

- id | BIGINT -AUTO_INCREMENT - PRIMARY_KEY (UNIQUE, NOTNULL)
- description | text - null
- id_degree_programme

## teachers

- id | BIGINT -AUTO_INCREMENT - PRIMARY_KEY (UNIQUE, NOTNULL)
- name | varchar (20) - not null
- surname | varchar (20) - not null
- email | varchar (20) - not null

## exam

- id | BIGINT -AUTO_INCREMENT - PRIMARY_KEY (UNIQUE, NOTNULL)
- name | varchar (20) - not null
- id_course_of_study

## students

- id | BIGINT -AUTO_INCREMENT - PRIMARY_KEY (UNIQUE, NOTNULL)
- name | varchar (20) - not null
- surname | varchar (20) - not null
- id_degree_programme

- email | varchar (20) - not null
- enrollment year | date - not null
- matricola | varchar(20) NOT NULL UNIQUE
