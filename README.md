# Veridion_PoC_Analysys

## Cum mi-am gandit alegerile

* *Prima data am incercat sa inteleg cu ce date am de lucrat, asa ca am extras coloanele si m-am uitat cam ce inseamna fiecare.*
* *Ca sa obtin cele mai bune match-uri pentru fiecare companie m-am uitat peste datele de input. Am observat ca pot avea companii pentru care numele de input sa coincida,dar tara si orasul nu si invers.*
* *In prima faza ma gandesc sa calculez scorurile pentru fiecare din cele 5 rezultate,si iau ca output scorul cel mai mare.Fiecare input va primi un scor in functie de importanta sa in cautarea companiei,suma scorurilor va fi maxim 100 -- aceasta abordare nu lasa niciun rand unmatched(insa ulterior este nevoie de o verificare pentru inconsistente)*
* *Dupa o prima rulare a scriptului am observat alegeri gresite(spre exemplu daca am o companie cu numele mai asemanator decat alta,desi este in tara gresita ea tot va fi aleasa). Asa ca m-am gandit la un tradeoff -> daca compania cautata nu se afla in tara dorita scad 80% din scorul matching-ului pe numele companiei.*
* *Am obsertvat ca sunt 3 tipuri de denumiri pentru companie. Pana acum comparam input_company_name doar cu company_name. Am ajuns la concluzia ca ar fi bine sa il compar cu fiecare in parte,apoi sa selectez maximul dintre ele.*
* *Ma gandesc ca ar fi o idee buna sa sortez companiile dupa scorul obtinut. De asememnea,cred ca cele cu un scor foarte mic ar trebui scoase din fisierul companiilor de top. De asemenea, am observat companii cu ultima data actualizata in 2024. Din ce am citit Veridion doreste ultimele date de actualitate, ma gandeam sa fac un fisier separat pentru acelea, sau sa gasesc din nou un criteriu pentru a pastra cele care au un scor foarte bun.*

---

## Setup 
clonare repo
```bash
python -m venv .venv
pip install -r requirements.txt