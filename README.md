### **Fent un formulari accessible**  

Partint d’un formulari HTML senzill, afegeix almenys **5 característiques d’accessibilitat** per fer-lo més inclusiu i fàcil d’utilitzar. **Justifica cada característica** amb una explicació clara del per què és important per a l’accessibilitat.  

Consulta el material del curs i els següents recursos si ho necessites:  
- [W3C Web Accessibility Initiative](https://www.w3.org/WAI/)  
- [W3Schools - Accessibility](https://www.w3schools.com/accessibility/)  
- [Happy Coding - Accessibility](https://happycoding.io/tutorials/accessibility)  

---

#### **Característiques d’accessibilitat suggerides:**  

1. **Estructura semàntica:**  
   - Fes servir etiquetes HTML semàntiques per crear una estructura clara i significativa.  
   - Inclou elements essencials del formulari com `<form>`, `<label>`, `<input>`, i `<button>`.  
   - Exemple:  
     ```html
     <form>
       <label for="username">Nom d'usuari:</label>
       <input type="text" id="username" name="username" required>
       <button type="submit">Enviar</button>
     </form>
     ```

2. **Rols i atributs ARIA:**  
   - Aplica rols i atributs ARIA per millorar l’accessibilitat.  
   - Usa atributs com `aria-labelledby`, `aria-required`, `aria-invalid`, i altres rellevants per descriure millor els camps i el seu estat.  
   - Exemple:  
     ```html
     <input type="text" id="email" name="email" aria-required="true" aria-labelledby="email-label">
     <span id="email-label">Correu electrònic</span>
     ```

3. **Accessibilitat amb teclat:**  
   - Assegura que el formulari es pugui navegar només amb el teclat.  
   - Defineix un ordre lògic de navegació amb `tabindex` i implementa estils de focus.  
   - Exemple:  
     ```html
     <button type="submit" tabindex="0">Enviar</button>
     ```

4. **Disseny visual i contrast:**  
   - Utilitza esquemes de color amb suficient contrast per als camps i botons.  
   - Considera la mida de lletra i la llegibilitat per a persones amb discapacitats visuals.  
   - Exemple (CSS):  
     ```css
     input {
       font-size: 16px;
       border: 1px solid #333;
       background-color: #fff;
       color: #000;
     }
     ```

5. **Gestió d’errors i validació:**  
   - Implementa validació del costat del client amb JavaScript i proporciona missatges d’error descriptius associats als camps del formulari.  
   - Exemple (JS i HTML):  
     ```html
     <input type="email" id="email" required aria-invalid="true">
     <span id="error-message" aria-live="polite">Aquest camp és obligatori i ha de ser un correu electrònic vàlid.</span>
     <script>
       const emailInput = document.getElementById('email');
       emailInput.addEventListener('input', function() {
         if (!emailInput.checkValidity()) {
           document.getElementById('error-message').style.display = 'block';
         } else {
           document.getElementById('error-message').style.display = 'none';
         }
       });
     </script>
     ```

6. **Text alternatiu i multimèdia:**  
   - Proporciona text alternatiu descriptiu per a imatges amb l’atribut `alt`.  
   - Assegura que els elements multimèdia (com vídeos) siguin accessibles.  
   - Exemple:  
     ```html
     <img src="captcha.png" alt="Codi CAPTCHA per verificar l'usuari">
     ```

7. **Disseny responsiu:**  
   - Crea un disseny adaptable a diferents dispositius.  
   - Optimitza el disseny del formulari per a pantalles petites i grans.  
   - Exemple (CSS):  
     ```css
     @media (max-width: 600px) {
       form {
         width: 100%;
         padding: 10px;
       }
     }
     ```

8. **Proves amb tecnologia assistiva:**  
   - Testeja el formulari amb lectors de pantalla i altres eines per garantir-ne l’accessibilitat.  

9. **Documentació i comentaris:**  
   - Inclou comentaris en el codi per explicar les decisions de disseny.  
   - Escriu un fitxer `README.md` que detalli les característiques d’accessibilitat implementades i el seu objectiu.  

---

#### **Exemple senzill de formulari accessible:**

```html
<form>
  <label for="username">Nom d'usuari:</label>
  <input type="text" id="username" name="username" required aria-required="true" aria-labelledby="username-label">
  <label for="email">Correu electrònic:</label>
  <input type="email" id="email" name="email" required aria-required="true" aria-invalid="false">
  <button type="submit">Enviar</button>
</form>
```

Aquest plantejament ofereix una base sòlida per treballar l’accessibilitat i la usabilitat d’un formulari mentre s’entenen conceptes clau i tècniques específiques. 😊

# Canvis Aplicats al Formulari per Millorar la seva Accessibilitat (WCAG)

## 1. **Associació de `label` amb els camps**

- He implementat l'atribut for en les tags `label` perque busqui la id dels inputs i així al aptretar els noms dels inputs automaticament entris al input fent mes facil accesdir-hi.

## 2. **Instruccions clares**

- S'han afegit instruccions descriptives mitjançant l'atribut `aria-describedby` per proporcionar informació addicional sobre camps específics, com ara el format del número de telèfon o els requisits de la contrasenya.

## 3. **Validació obligatòria**

- Els camps obligatoris inclouen l'atribut `required` i `aria-required="true"`. Això fa que els usuaris rebin una alerta al no omplir el camp.

## 4. **Enfocament visible**

- He implementat que en els `inputs`, `selects` i `buttons` al estar dintre d'ells o com llegeix html `focused` fa que l'usuari visualment vegi que si que ha entrat en l'input o esta sobre el botó que necessita.

## 5. **Colors amb bon contrast**

- Els colors de text i fons compleixen amb els requisits mínims de contrast per assegurar que siguin llegibles per a persones amb discapacitats visuals.

## 6. **Elements interactius accessibles**

- Els botons i altres elements interactius tenen atributs com `aria-label` per proporcionar informació addicional als usuaris de tecnologies assistives.

## 7. **Missatges d'error accessibles**

- Els missatges d'ajuda o error s'associen directament amb els camps pertinents mitjançant `aria-describedby`
