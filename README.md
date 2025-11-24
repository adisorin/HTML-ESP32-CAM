# HTML-ESP32-CAM Viewer

<img width="854" height="888" alt="image" src="https://github.com/user-attachments/assets/304eb9a0-9a56-4689-b99d-eccaabeac953" />

# ❌ Eroare la conectare! Verifică IP-ul sau portul.
<img width="855" height="891" alt="image" src="https://github.com/user-attachments/assets/9ad91e20-2b04-4d86-ab1a-4f08ded3ff90" />
# Conectare
<img width="854" height="892" alt="image" src="https://github.com/user-attachments/assets/89c5f543-09cc-4546-ae2e-3c63a0d863e0" />

📌 Prezentarea aplicației „ESP32-CAM Viewer cu IP-uri Locale”
Această aplicație web este o interfață creată pentru a vizualiza fluxul video (stream-ul) generat de un modul ESP32-CAM, atât din rețeaua locală, cât și din exterior (prin un domeniu DDNS, exemplu GO.RO). Pagina este proiectată astfel încât să ofere o navigare ușoară, feedback vizual clar și gestionare robustă a conexiunilor.

🎨 Design și structură vizuală
Interfața este simplă și modernă.
Pagina folosește o structură centrată, cu:
un titlu clar („ESP32-CAM Viewer”);

trei butoane mari de control:
Conectare Locală, Conectare Externă, Deconectare;
o zonă mare tip cadru pentru afișarea stream-ului video;
o listă de IP-uri locale detectabile, prezentate sub formă de butoane;
mesaje de status pentru informarea utilizatorului.

Elementele vizuale includ:
efecte de hover și animație,
spinner animat în timpul conectării,
mesaje de eroare animate (shake),
culori intuitive: albastru pentru conectare, verde pentru extern, roșu pentru deconectare.

🔌 Ce face aplicația?
Aplicația permite utilizatorului să se conecteze la camera ESP32 în trei moduri:

1. Conectare Locală
Accesează dispozitivul pe IP-ul intern stabilit în rețea.

2. Conectare Externă (GO.RO)
Folosește un domeniu DDNS, util când camera este accesată din afara rețelei.

3. Conectare la un IP local din listă
Sunt afișate mai multe IP-uri prestabilite, utile dacă există mai multe camere în rețea.

4. Deconectare
Oprește fluxul video și curăță complet zona video.

⚙️ Cum funcționează tehnic?

Gestionarea fluxului de imagini

Când utilizatorul selectează un IP:

aplicația resetează orice conexiune anterioară;

afișează un spinner animat în locul stream-ului;

încearcă să încarce un obiect <img> cu sursa http://IP/stream.


Dacă imaginea se încarcă cu succes:

spinnerul dispare,

stream-ul este afișat în fereastră.


Dacă se produce o eroare:
conexiunea este anulată,
apare un mesaj roșu animat de eroare.

🛡️ Mecanism de protecție al conexiunilor
Codul folosește un sistem inteligent bazat pe connectionId:
Fiecare încercare de conectare primește un ID unic.
Dacă utilizatorul apasă apoi Alt buton într-un timp scurt,
vechile evenimente onload sau onerror sunt ignorate automat.
Astfel se evită situațiile în care o conexiune veche suprascrie o conexiune nouă.
Este o metodă elegantă de a preveni erorile și conflictele între conexiuni rapide consecutive.

🧹 Managementul dezactivării stream-ului
Funcția disconnect():
resetează connectionId pentru a invalida orice apel vechi,
șterge sursa imaginii,
golește cadrul video,
actualizează vizual starea la „Deconectat”.

🚨 Gestionarea erorilor
Funcția handleError():
apelează deconectarea,
afișează un mesaj clar de eroare,
schimbă culoarea statusului în roșu,
folosește o mică animație "shake" pentru a evidenția problema.

🔍 Funcția listei de IP-uri locale
Codul creează automat butoane pentru fiecare IP local, oferind acces rapid la camere multiple din rețea.

⭐ Concluzie
Această pagină este o interfață completă și intuitivă pentru controlul și vizualizarea unui ESP32-CAM, oferind:
conectare rapidă,
feedback vizual profesionist,
siguranță la schimbarea conexiunilor,
listă de IP-uri multiple,
gestionarea corectă a erorilor.
Este o soluție practică, elegantă și eficientă pentru supraveghere video sau testarea modulelor ESP32-CAM în rețea.
