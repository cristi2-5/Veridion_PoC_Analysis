# Veridion_PoC_Analysys

## Cum mi-am gandit alegerile(partea de selectie a celei mai bune variante din cele 5)

* *Prima data am incercat sa inteleg cu ce date am de lucrat, asa ca am extras coloanele si m-am uitat cam ce inseamna fiecare.*
* *Ca sa obtin cele mai bune match-uri pentru fiecare companie m-am uitat peste datele de input. Am observat ca pot avea companii pentru care numele de input sa coincida,dar tara si orasul nu si invers.*
* *In prima faza ma gandesc sa calculez scorurile pentru fiecare din cele 5 rezultate,si iau ca output scorul cel mai mare.Fiecare input va primi un scor in functie de importanta sa in cautarea companiei,suma scorurilor va fi maxim 100 -- aceasta abordare nu lasa niciun rand unmatched(insa ulterior este nevoie de o verificare pentru inconsistente)*
* *Dupa o prima rulare a scriptului am observat alegeri gresite(spre exemplu daca am o companie cu numele mai asemanator decat alta,desi este in tara gresita ea tot va fi aleasa). Asa ca m-am gandit la un tradeoff -> daca compania cautata nu se afla in tara dorita scad 80% din scorul matching-ului pe numele companiei.*
* *Am obsertvat ca sunt 3 tipuri de denumiri pentru companie. Pana acum comparam input_company_name doar cu company_name. Am ajuns la concluzia ca ar fi bine sa il compar cu fiecare in parte,apoi sa selectez maximul dintre ele.*
* *Am observat campul locations, o alta alternativa pentru un match cat mai acurate ar fi sa dau split la acele adrese si sa iau scorul maxim in urma aplicarii functiei calculate_score,dar din ce am vazut cea mai buna este mereu prima(cea utilizata in input)*


## Cum mi-am gandit alegerilea(partea de inconsistente si cleanup)
* *Prima data am ales sa elimin coloanele care au peste 85% din date lipsa,deoarece nu ofera niciun plus de valoare in statistica finala(asigurandu-ma ca nu sunt date critice care in unele cazuri ar fi facut diferenta)*
* *De asemenea, voi elimina randurile care au fost updatate inainte de vara lui 2024,deoarece consider ca nu mai sunt de actualitate si pot prezenta niste cifre false*
* *Companiile selectate care au un scor foarte mic(<40) le voi elimina, intrucat ne intereseaza doar cele mai bune match-uri in raportul final*
* *Randurile pe care le-am sters mai sus as vrea sa le bag intr-un nou fisier,apoi sa apelez API-ul de la Veridion pentru a putea vedea daca obtin rezultate mai bune*
* *Am stat si m-am gandit unde as putea gasi inconsistente si cred ca singurele coloane relevante sunt employees,revenue si coloanele ce folosesc coduri pentru standardizare precum: NAICS,SIC,ISIC,NACE,SICS,IBC.*
 

---

## Setup 
clonare repo
```bash
python -m venv .venv
pip install -r requirements.txt