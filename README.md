# wpquiz
How to make a quiz with short answers in word press

If you're interested in test / quiz to introduce in your posts in word press you should use Script n Style plugin (add plugin in word press) and then put some shortcode in the page that you will find in this repository.

*How to make a single question*
Each question is like 

input("The capital of Italy is ","Rome", "the ethernal city.");

this will make a sentence with an input box that requires rome as the right answer.

*This is an example*

    <script>
        // use input("part1,"answer","part2*"); // * is to glue two answers, not mandatory
        // use guessWhat("part1,"answer answer","part2*");
        // if you digit 'aiuto' in the input box you will see the first 3 letter in the input box itself
        // usa # davanti a una frase per creare alternative



    function check(casella, giusta, num){
        giusta = giusta.toLowerCase();
        casella.value = casella.value.toLowerCase();
            if (casella.value == 'aiuto'){
            if (casella.value.length >= 3){
            casella.value = giusta[0]+giusta[1]+ giusta[2]
            }
        }
        else{
        if (casella.value.includes(giusta)){
            casella.style.background = 'yellow';
            return casella.value.includes(giusta);
        }
        else{
            casella.style.background = 'red';
        }
    }
    }

    function checkWhat(casella, giusta, num){
        giusta = giusta.toLowerCase();
        casella.value = casella.value.toLowerCase();
        if (casella.value == 'aiuto'){
            if (casella.value.length >= 3){
            casella.value = giusta[0]+giusta[1]+ giusta[2]
            }
        }
        else {
        for (r of giusta.split(" ")){
        if (casella.value.includes(r)){
            casella.style.background = 'yellow';
            return casella.value.includes(giusta);
        }
            else{
            casella.style.background = 'red';
        }
        }
    }

    }


    function print_it(parola){
        if (soluzioni.innerHTML.includes(parola)){
        }
        else {
            soluzioni.innerHTML += " - " + parola;
        }
    }

    var sol = [];
        var countdom = 0;

        function input(dom_s, giusta, dom_e){
            var inizio = "";
            var fine = "";
            sol[countdom] = giusta;
            var repls = giusta[0];
            if (giusta.includes("*")){
                giusta = giusta.replace("*", "");
                repls = "";
            };
            num = countdom + 1
            countdom++
            var dom_h2 = inizio + dom_s;
            if (giusta != " "){
            var part1 = dom_h2 + "<input style='font-size:30;display:inline;' type=text class='t1' placeholder='" + repls + "....' onchange=\"if (check(this,'";
            part1 += giusta + "')){print_it(this.value)};\" /><td>" + dom_e + fine;
        }
        else {
            var part1 = dom_h2 + dom_e + fine;

        }
            document.write(part1);
        }


        function guessWhat(dom_s, giusta, dom_e){
            dom_s = dom_s.replace("#"," ");
            var inizio = "";
            var fine = "";
            sol[countdom] = giusta;
            num = countdom + 1
            countdom++
            var dom_h2 = inizio + dom_s;
            var part1 = dom_h2 + "<input style='font-size:30;display:inline;' type=text class='t1' placeholder='" + giusta[0] + "....' onchange=\"if (checkWhat(this,'";
            part1 += giusta + "')){print_it(this.value)};\" /><td>" + dom_e + fine
            document.write(part1);
        }


    function addsol(){
        document.write("<div id='soluzioni'>Suggerimenti: </div>");
        sol.sort();
        for (s of sol){
            soluzioni.innerHTML += " [" + s[0] + s[1] + s[2] + "] ";
        }
    }

    document.write("<p style='font-size:1,2em;'>");
    input("Le imprese turistico ristorative sono imprese industriali o commerciali? ", "*commerciali",".");
    input("Per dare vita ad una nuova imprese occorre inviare la Comunicazione Unica d'impresa all'INPS, alla CCIA, all'INAIL o all'Agenzia delle entrate? ", "CCIAA",".");
    input("<h2>Le imprese ristorative</h2>Le imprese ristorative svolgono attività di  ", "preparazione",",");
    input(" ", "conservazione",",");
    input("e ", "somministrazione","di alimenti e bevande.");
    input("<br>Si dividono in due categorie: <br>ristorazione ", "commerciale","<br>");
    input("e ristorazione ", "collettiva",", detta anche ristorazione industriale, che comprende le mense");
    input("e il settore ", "catering","");
    input("<h1>La ristorazione commerciale</h1>Comprende i ristoranti tradizionali, la ristorazione semplificata, la ristorazione rapida, i ristoranti di agriturismi e quelli degli alberghi.",' ',' ');
    input("<ol><li>I ristoranti tradizionali servono diversi tipi di cucina. Si può trattare di ristoranti etnici, macrobiotici ecc.",' ',' ');
    input("<li>La ristorazione semplificata propone una varietà di pietanze più lilmitata rispetto ai ristoranti tradizionali (trattorie, le osterie, pizzerie, rosticcerie).",' ',' ');
    input("<li>La ristorazione rapida offre menu fissi o solo alcuni prodotti ad elevato livello di rotazione (fast food, le paninoteche, i bar e le pizzerie da asporto)",' ',' ');
    input("<li>Le imprese agrituristiche o alberghiere offrono un servizio complementare rispetto all'attività principale. Per i clienti, il ristorante nell'hotel rappresenta un servizio estremamente comodo, perché permette di consumare i pasti senza doversi spostare dal luogo in cui pernottano. È adatto soprattutto per gli alberghi utilizzati da persone che si spostan per lavoro e non per vacanza, in quanto quest'ultimi preferiscono spostarsi per visitare i luoghi di vacanza.</ol>",' ',' ');
    input("<h2>Quali sono le imprese della ristorazione collettiva?</h2>",' ',' ');
    input("Si rivolgono a clienti che per motivi di necessità (lavoro o studio) consumano il pasto trovandosi in un luogo diverso dalla propria dimora abituale.",' ',' ');
    input("La ristorazione collettiva può essere aziendale, istituzionale, per banchetti e per trasporti.",' ',' ');
    input("La ristorazione aziendale può essere effettuata con il metodo del self-service, per le aziende che dispongono dei locali dove consumare i pasti, o attraverso i buoni pasto da usare presso i ristoranti convenzionati, per le aziende che non hanno lo spazio dove somministrare i pasti.",' ',' ');
    input("la ristorazione isituzionale comprende le mense scolastiche o universitarie ecc.",' ',' ');
    input("La ristorazione per banchetti (banqueting) riguarda gli eventi come cerimonie e convegni in cui l'impresa si occupa anche dell'organizzazione dell'evento, oltre a fornire cibi e bevande.",' ',' ');
    input("La ristorazione per trasporti comprende la fornitura di pasti e bevande sui mezzi di trasporto e le attività di catering destinate ai viaggiatori e svolte lungo le reti stradali.",' ',' ');
    input("Struttura organizzativa delle imprese ristorative",' ',' ');
    input("I settori delle imprese ristorativi sono la cucina, la sala, gli approvvigionamenti e l'amministrazione.",' ',' ');
    input("Nella ristorazione commerciale i cibi vengono preparati e consumati immediatamente, con un lavoro della cucina e della sala che si svolge in modo coordinato.",' ',' ');
    input("In quella collettiva, invece, le operazioni di preparazione e distribuzione dei pasti è effettuata in tempi e luoghi diversi con l'aggiunta di operazioni di trasporto e conservazione.",' ',' ');
    input("Forma organizzativa di tipod gerarchico",' ',' ');
    input("Sono le forme assunte dalle imprese di piccole dimensioni: al vertice c'è il titolare, mentre alla bas ci sono i dipendenti che si occupano della cucina, della sala e dell'amministrazione, spesso con una sovrapposizione dei ruoli.",' ',' ');
    input("Nelle imprese di grandi dimensioni l'organizzazione non è gerarchica, ma funzionale. La direzione è affidata al manager al disotto del quale operano dei direttori distinti per funzione. Nei ristoranti tradizonali ci sono i direttori di cucina e di sala. nella ristorazione collettiva ci sono i direttori delle singole mense.",' ',' ');
    document.write("</p>");
    //addsol();


    </script>
