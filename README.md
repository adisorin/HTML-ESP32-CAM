# HTML-ESP32-CAM Viewer

<img width="854" height="888" alt="image" src="https://github.com/user-attachments/assets/304eb9a0-9a56-4689-b99d-eccaabeac953" />

# ❌ Eroare la conectare! Verifică IP-ul sau portul.
<img width="855" height="891" alt="image" src="https://github.com/user-attachments/assets/9ad91e20-2b04-4d86-ab1a-4f08ded3ff90" />

# Conectare
<img width="854" height="892" alt="image" src="https://github.com/user-attachments/assets/89c5f543-09cc-4546-ae2e-3c63a0d863e0" />


# ESP32-CAM AI Viewer

<img width="763" height="881" alt="image" src="https://github.com/user-attachments/assets/1f69c288-d750-4158-8109-6c93f8c7dd69" />
<img width="703" height="519" alt="image" src="https://github.com/user-attachments/assets/ab533132-f76e-4187-8ea9-f14a0a93b431" />



📌 Prezentarea aplicației „ESP32-CAM Viewer cu IP-uri Locale”
Această aplicație web este o interfață creată pentru a vizualiza fluxul video (stream-ul) generat de un modul ESP32-CAM, atât din rețeaua locală, cât și din exterior (prin un domeniu DDNS, exemplu GO.RO). Pagina este proiectată astfel încât să ofere o navigare ușoară, feedback vizual clar și gestionare robustă a conexiunilor.
# Nou:
În ESP32-CAM AI Viewer se poate face captură video și downloada automat direct pe PC sau telefon dacă AI este ACTIV.

# 🎨 Design și structură vizuală

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

# 🔌 Ce face aplicația?
Aplicația permite utilizatorului să se conecteze la camera ESP32 în trei moduri:

1. Conectare Locală
Accesează dispozitivul pe IP-ul intern stabilit în rețea.

2. Conectare Externă (GO.RO)
Folosește un domeniu DDNS, util când camera este accesată din afara rețelei.

3. Conectare la un IP local din listă
Sunt afișate mai multe IP-uri prestabilite, utile dacă există mai multe camere în rețea.

4. Deconectare
Oprește fluxul video și curăță complet zona video.

# ⚙️ Cum funcționează tehnic?

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

# 🛡️ Mecanism de protecție al conexiunilor

Codul folosește un sistem inteligent bazat pe connectionId:

Fiecare încercare de conectare primește un ID unic.

Dacă utilizatorul apasă apoi Alt buton într-un timp scurt,

vechile evenimente onload sau onerror sunt ignorate automat.

Astfel se evită situațiile în care o conexiune veche suprascrie o conexiune nouă.

Este o metodă elegantă de a preveni erorile și conflictele între conexiuni rapide consecutive.

# 🧹 Managementul dezactivării stream-ului

Funcția disconnect():

resetează connectionId pentru a invalida orice apel vechi,

șterge sursa imaginii,

golește cadrul video,

actualizează vizual starea la „Deconectat”.

# 🚨 Gestionarea erorilor

Funcția handleError():

apelează deconectarea,

afișează un mesaj clar de eroare,

schimbă culoarea statusului în roșu,

folosește o mică animație "shake" pentru a evidenția problema.

# 🔍 Funcția listei de IP-uri locale

Codul creează automat butoane pentru fiecare IP local, oferind acces rapid la camere multiple din rețea.

# ⭐ Concluzie

Această pagină este o interfață completă și intuitivă pentru controlul și vizualizarea unui ESP32-CAM, oferind:

conectare rapidă,

feedback vizual profesionist,

siguranță la schimbarea conexiunilor,

listă de IP-uri multiple,

gestionarea corectă a erorilor.

Este o soluție practică, elegantă și eficientă pentru supraveghere video sau testarea modulelor ESP32-CAM în rețea.
---
# English language:

# HTML-ESP32-CAM Viewer

<img width="854" height="888" alt="image" src="https://github.com/user-attachments/assets/304eb9a0-9a56-4689-b99d-eccaabeac953" />

# ❌ Connection Error! Check the IP or port.

<img width="855" height="891" alt="image" src="https://github.com/user-attachments/assets/9ad91e20-2b04-4d86-ab1a-4f08ded3ff90" />

# Connect

<img width="854" height="892" alt="image" src="https://github.com/user-attachments/assets/89c5f543-09cc-4546-ae2e-3c63a0d863e0" />

# ESP32-CAM AI Viewer

<img width="763" height="881" alt="image" src="https://github.com/user-attachments/assets/1f69c288-d750-4158-8109-6c93f8c7dd69" />
<img width="703" height="519" alt="image" src="https://github.com/user-attachments/assets/ab533132-f76e-4187-8ea9-f14a0a93b431" />

📌 **Presentation of the “ESP32-CAM Viewer with Local IPs” Web App**

This web application provides an interface designed to view the video stream generated by an ESP32-CAM module — both from the local network and externally (via a DDNS domain such as GO.RO).
The page is built to offer easy navigation, clear visual feedback, and robust connection handling.

# New
In ESP32-CAM AI Viewer, you can capture video and automatically download it directly to your PC or phone if AI is ACTIVE.

---

# 🎨 Visual Design & Layout

The interface is simple and modern.

The page uses a centered layout with:

* a clear title (“ESP32-CAM Viewer”)
* three large control buttons:

  * Local Connect, External Connect, Disconnect
* a large frame area for displaying the video stream
* a list of detectable local IPs displayed as buttons
* status messages for user feedback

Visual elements include:

* hover effects and animations
* a loading spinner while connecting
* animated error messages (shake effect)
* intuitive colors: blue for local connect, green for external, red for disconnect

---

# 🔌 What Does the App Do?

The application allows the user to connect to the ESP32-CAM camera in three ways:

### 1. Local Connection

Accesses the device via its internal IP address within the network.

### 2. External Connection (GO.RO / DDNS)

Uses a DDNS domain, useful when accessing the camera from outside the network.

### 3. Connect to a Local IP from the List

Displays several preset local IPs — useful when multiple cameras exist in the same network.

### 4. Disconnect

Stops the video stream and clears the display area.

---

# ⚙️ How Does It Work Technically?

### Image Stream Handling

When the user selects an IP:

* the app resets any previous connection
* shows an animated spinner instead of the stream
* attempts to load an `<img>` object with the source `http://IP/stream`

If the image loads successfully:

* the spinner disappears
* the video stream becomes visible

If an error occurs:

* the connection is canceled
* a red animated error message is displayed

---

# 🛡️ Connection Protection Mechanism

The code uses an intelligent system based on **connectionId**:

* Each connection attempt receives a unique ID.
* If the user quickly presses another button,
  older `onload` or `onerror` events are automatically ignored.

This prevents situations where an old connection overrides a new one — an elegant solution to avoid conflicts during rapid connection switching.

---

# 🧹 Stream Deactivation Management

The `disconnect()` function:

* resets `connectionId` to invalidate any old calls
* clears the image source
* empties the video frame
* visually updates the state to "Disconnected"

---

# 🚨 Error Handling

The `handleError()` function:

* triggers a disconnect
* displays a clear error message
* changes the status color to red
* uses a small "shake" animation to highlight the issue

---

# 🔍 Local IP List Functionality

The code automatically creates buttons for each local IP, offering quick access to multiple cameras on the network.

---

# ⭐ Conclusion

This page is a complete and intuitive interface for controlling and viewing an ESP32-CAM, offering:

* fast connection
* professional visual feedback
* safe connection switching
* multiple IP selection
* proper error management

# A practical, elegant, and efficient solution for video surveillance or testing ESP32-CAM modules within a network.
