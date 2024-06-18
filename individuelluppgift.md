
## Beskrivning av vad jag har bidragit med under grupparbetet

Jag har skapat en del av vår webbapplikation som låter användare registrera sig. Här är hur jag har gjort det:

Registreringskontrollern (Registration):

Det är som en chef som tar hand om allt som händer när någon försöker registrera sig på vår webbsida.
Användning av andra delar av koden:

Jag har tagit hjälp av PasswordEncoder och UserDetailsService för att kryptera lösenord och hantera användarinformation.
Hur registreringen fungerar:

När någon vill registrera sig, visar jag ett formulär där de kan fylla i sina uppgifter.
När de skickar in formuläret, kollar min kod om det finns några fel i uppgifterna de fyllde i.
Om allt är rätt, krypterar jag deras lösenord för att hålla det säkert.
Sedan skapar jag ett användarkonto och sparar det tillfälligt så att de kan logga in senare.
Jag sparar också deras e-postadress så att vi kan kontakta dem om det behövs.
Hur jag lagrar informationen:

Jag använder en speciell typ av minne (InMemoryUserDetailsManager) för att spara användarkontot temporärt.

## Fråga 1: Metod i webbapplikationen

 @PostMapping
    public String registerUser(@Valid @ModelAttribute("user") UserApp appUser, BindingResult bindingResult, Model model){
        // Kontrollerar om det finns valideringsfel i formuläret
        if(bindingResult.hasErrors()){
            model.addAttribute("error", "There are errors in the form, please correct them");
            System.out.println(appUser); // Debugging: Skriver ut användardetaljerna till konsolen
            return "register"; // Returnerar vyn "register" för att korrigera fel
        }

## Fråga 2: Vad innebär ordet public/private i metodsignaturen?

Public: Metoden kan användas och anropas från andra klasser.
Private: Metoden kan bara användas inom samma klass där den är deklarerad.

## Fråga 3: Vad innebär det om det står 'void'? Vad innebär det om det står en typ eller klass?

Void: Metoden returnerar inget värde.
Typ eller klass: Metoden returnerar ett värde av den specificerade datatypen eller klassen.

## Fråga 4: Vilken namnkonvention finns för metoder i Java?

Metodnamn i Java börjar vanligtvis med ett verb i små bokstäver, följt av substantiv eller adjektiv. Exempelvis calculateTotal(), getUserDetails().

## Fråga 5: Vad innebär det om det inte står något mellan paranteserna?

Det innebär att metoden inte tar emot några parametrar eller argument när den anropas.

## Fråga 6: Vad kallas det som skickas med till metoden mellan paranteserna?

Det som skickas med till metoden mellan paranteserna kallas antingen parametrar eller argument.

## Fråga 7: Hur ska du skriva för att returnera summan av a och b i denna metod?

public int add(int a, int b){
    return a + b;
}

## Fråga 8: Hur ser det ut när man anropar denna metod från en annan metod?

// Anrop av add-metoden från en annan metod
int sum = add(5, 3);


## Fråga 9: Skapa en klass med tom konstruktor

public class HakansClass {
    // Tom konstruktor
    public HakansClass() {
    }
}


## Fråga 10: Skillnaden på objekt och primitiva typer i Java

// Skapande av primitiv typ med ett värde
int number = 10;

// Skapande av ett objekt (instans av en klass)
String text = new String("Hello");


## Fråga 11: Namnkonvention i Java för metoder

I Java börjar metodnamn vanligtvis med ett verb, såsom calculateSomething() eller getUserDetails().

<!-- Inkludera den färgade strukturen från colors.md -->
<object data="colors.md" type="text/html" width="800px" height="600px" style="overflow:auto;border:1px solid #ccc"></object>
