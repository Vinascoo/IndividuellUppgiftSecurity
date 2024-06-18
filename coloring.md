<!DOCTYPE html>
<html>
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            color: #333;
            margin: 20px;
        }
        .section {
            background-color: #e0e0e0;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 5px;
        }
        .question {
            font-size: 18px;
            color: #4CAF50;
            margin-bottom: 5px;
        }
        .answer {
            margin-left: 20px;
            margin-bottom: 10px;
        }
        code {
            background-color: #f1f1f1;
            padding: 2px 5px;
            border-radius: 3px;
        }
    </style>
</head>
<body>

<div class="section">
    <h2>Beskrivning av vad jag har bidragit med under grupparbetet</h2>
    <div class="answer">
        Jag har bidragit med implementationen av användarregistrering och hantering av användardata i vår grupps webbapplikation. Nedan följer en förklaring och exempelkod på en metod från vårt projekt.
    </div>
</div>

<div class="section">
    <div class="question">Fråga 1: Metod i webbapplikationen</div>
    <div class="answer">
        <code>
            // Exempel på metod för att registrera användare
            @PostMapping("/register")
            public String registerUser(@Valid @ModelAttribute("user") UserApp appUser, BindingResult bindingResult, Model model){
                if(bindingResult.hasErrors()){
                    model.addAttribute("error", "Det finns fel i formuläret, vänligen korrigera dem");
                    return "register";
                }
                String encodedPassword = passwordEncoder.encode(appUser.getPassword());
                appUser.setPassword(encodedPassword);
                
                // Skapar UserDetails och lägger till användaren i en in-memory manager
                UserDetails newUser = User.withUsername(appUser.getUsername())
                        .password(appUser.getPassword())
                        .roles("USER")
                        .build();
                ((InMemoryUserDetailsManager) userDetailsService).createUser(newUser);
                
                userEmails.put(appUser.getUsername(), appUser.getEmail());
                
                model.addAttribute("user", appUser);
                model.addAttribute("username", appUser.getUsername());
                
                return "registerSuccessful";
            }
        </code>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 2: Vad innebär ordet public/private i metodsignaturen?</div>
    <div class="answer">
        <p>Public: Gör metoden tillgänglig för alla andra klasser.</p>
        <p>Private: Gör metoden endast tillgänglig för den egna klassen.</p>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 3: Vad innebär det om det står 'void'? Vad innebär det om det står en typ eller klass?</div>
    <div class="answer">
        <p>Void: Metoden returnerar ingen värde.</p>
        <p>Typ eller klass: Metoden returnerar ett värde av den specificerade typen eller klassen.</p>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 4: Vilken namnkonvention finns för metoder i Java?</div>
    <div class="answer">
        <p>Metodnamn i Java börjar vanligtvis med ett verb i små bokstäver, följt av substantiv eller adjektiv.</p>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 5: Vad innebär det om det inte står något mellan paranteserna?</div>
    <div class="answer">
        <p>Det innebär att metoden inte tar emot några parametrar.</p>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 6: Vad kallas det som skickas med till metoden mellan paranteserna?</div>
    <div class="answer">
        <p>Parametrarna som skickas med till metoden kallas ofta argument eller inparametrar.</p>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 7: Hur ska du skriva för att returnera summan av a och b i denna metod?</div>
    <div class="answer">
        <code>
            public int add(int a, int b){
                return a + b;
            }
        </code>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 8: Hur ser det ut när man anropar denna metod från en annan metod?</div>
    <div class="answer">
        <code>
            // Exempel på anrop av add-metoden
            int sum = add(5, 3);
        </code>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 9: Skapa en klass med tom konstruktor</div>
    <div class="answer">
        <code>
            public class HakansClass {
                // Tom konstruktor
                public HakansClass() {
                }
            }
        </code>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 10: Skillnaden på objekt och primitiva typer i Java</div>
    <div class="answer">
        <code>
            // Skapa en primitiv typ med ett värde
            int number = 10;

            // Skapa ett objekt (en instans av en klass)
            String text = new String("Hello");
        </code>
    </div>
</div>

<div class="section">
    <div class="question">Fråga 11: Namnkonvention i Java för metoder</div>
    <div class="answer">
        <p>I Java brukar man börja metodnamn med ett verb, exempelvis "calculateSomething()" eller "getUserDetails()".</p>
    </div>
</div>

</body>
</html>