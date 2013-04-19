OMPSSC-Service
==============

OMPSS-Service mazgu kontrolinio mazgo ( *OMPSS-Controller* ) *OpenStack* debeises platformoi diegimo skriptai.

Sis projektas neturi *OMPSS-Controller* paslaugos iseities kodu. 
*OMPSS-Controller* projekta galima rasti pasinaudojus sia nuoroda:
https://github.com/nereliz/OMPSS-Controller

Internetinio matematinio programavimo ir projektavimo serverines paslaugos projekta galima rasti 
pasinaudojus sia nuoroda:
https://github.com/nereliz/OMPSS-Server

Diegimas:
--------------

Sukurkite aplanka *~/src/juju/charms/precise*

    mkdir ~/src/juju/charms/precise

Tada i naujaji aplanka klonuokite projekta
    
    cd ~/src/juju/charms/precise
    git clone https://github.com/nereliz/OMPSSC-Service.git ompssc

Po to parsiusta paslauga ikeliamae i debesi

    cd ~/src/juju/charms/
    juju deploy --repository . local:precise/ompssc

Patalpine pasaluga sujungiame su ompss paslauga kuri siuo metu jau turetu buti ikelta i debesi

    juju add-relation ompss ompssc
    
Paviesiname paslauga

    juju expose ompssc

Konfiguravimas:
--------------

Reikalingi IP adresai nustatomi pagal domena, todel reiketu patirkinti *hooks/ompss-relation-joined* 
ir *hooks/ompss-relation-departed*ar domenas teisingai pertvarkomas norint gauti sistemai suprantama domena.
Siuo metu gautas domenas yrasuskaldomas per taska jei taskas yra randamas ir priekine dalis naudojama kaip 
naujasis domenas IP adresui gauti. Pvz: mazgas1.localadmin po pertvarkymo taps mazgas1.

Copyright (c) 2010 - 2013 Nerijus Barauskas

Projektas realizuotas kaip dalis baigimojo magistraturos darbo Siauliu Universitete.
