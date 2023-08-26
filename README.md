# AutoDisposition
Es es un script que se ejecuta en una página web. 
Su objetivo principal es escuchar o leer las entradas de texto en un campo de notas y, dependiendo de ciertas palabras clave ingresadas, realizar acciones específicas, como seleccionar casillas de verificación y agregar más texto.


## **Primer paso**

Instalar Tampermonkey.



Usen el siguiente link para instalar la extensión de tampermonkey y agregarla al GoogleChrome.

   [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?gclid=CjwKCAjwoqGnBhAcEiwAwK-OkUIZCOn8Kda71RifLQscCERVec4mdnvtzVGfAP_9vKnkuFnMUNH4XxoClCsQAvD_BwE)

Una vez instalado vamos a buscar la herramienta en la barra de extensiones.

![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/9c919865-baa2-4114-af7b-e64c0d578279)

Se debe ver de esta manera.

![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/95e69e34-1e2e-462f-aab1-58a1ae90ff23)


Vamos a darle click derecho y se va abrir un nuevo menú dónde seleccionaremos la opcion de "Dashboard"
![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/7afcd0f2-a672-4f1b-ad59-9c7ac3683a77)


## **Segundo Paso**

Montar el script.

En esta misma página al inicio hay dos archivos, uno de ellos se llama `Prod. Auto Disposition.user`, debemos darle click.
![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/c3a81714-893f-4821-9030-ec6cfc6ad55e)

Se desplegará el código del programa, ignorenlo por ahora, descargaremos el archivo dando click en el boton de descargar y lo guardaremos.
![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/4b34b9f4-e02b-44e2-915e-04d275ce52b4)

### Regresamos a la pestaña de "Dashboard" que abrimos antes en Tampermonkey para agregar el código.

Vamos a ir a la seccion de "Utilities" arriba a la derecha y luego en "Import from file" vamos a dar click en "Choose File"
![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/8ae66644-78c3-41f5-b438-77076ec271e4)

Se abrirá una nueva ventana donde debemos buscar y seleccionar el archivo que recién descargamos llamado `Prod. Auto Disposition.user`

Una vez seleccionado el archivo veremos una pantalla de confirmar la instalación, le daremos click a "Install"
![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/85712b84-7619-4b03-901f-dd44cca4f67d)

Y para verificar que todo se instaló correctamente iremos a "Installed Userscripts" y ahi veremos el archivo.
![image](https://github.com/TellezMan/AutoDisposition/assets/125960140/5c155f9a-9fa0-4842-aeb5-73aa33cec5c2)

## **Tercer Paso**
Editar el "script" y agregar nuestras notas.

[Codigos GoogleSheets](https://docs.google.com/spreadsheets/d/1_IxemQrdlmjzcBF5Zs8_o3xQMXYH2cQ9-PHP6wnORpE/edit?usp=sharing)

1. Copia el fragmento de código de abajo.
2. Pégalo justo antes de donde dice `"//================================FIN NOTAS====================================".`
3. Reemplaza `PALABRA_CLAVE` con la palabra clave que quieres detectar.
4. Completa los campos correspondientes como se explica a continuación:

     EXPLICACIÓN DEL CÓDIGO
    ```
   else if (value.includes('PALABRA_CLAVE')) {
            checkboxesToCheck = ["CODIGO1", "CODIGO2"];     // Añade los códigos de las casillas que quieres marcar estan en el google sheets.
            //checkboxesToUnCheck = ["CODIGO3", "CODIGO4"]; // Añade los códigos de las casillas que quieres desmarcar que están en el Google Sheets (se debe remover el "//" del principio)
            textToAdd = "TEXTO_A_AÑADIR";                   // Añade la nota que quieres que se agregue.
            textToRemove = 'PALABRA_CLAVE';                 // Indica la palabra clave nuevamente.
            setMoodAndSatisfaction();}                      // No cambies esta línea. Es una función que se llama después.



FRAGMENTO DE CODIGO A COPIAR



           else if (value.includes('')) {
                    checkboxesToCheck = [];
                    //checkboxesToUnCheck = [];
                    textToAdd = "";
                    textToRemove = '';
                    setMoodAndSatisfaction();}
   


## Mas detalles sobre el codigo.
1. Encabezado del Script: Esta parte del código define el nombre, la versión, la descripción, el autor y otros metadatos del script.
   
2. Variables Globales:
    - `notesField` - Es el campo de texto donde los se escriben las notas.
    - `satisfied` y `mood` - Son casillas de verificación que se seleccionan automáticamente dependiendo de la entrada.

3. Funciones:
    - `setMoodAndSatisfaction()`: Esta función simplemente establece ciertas casillas de verificación a un estado específico.

4. Evento de entrada: Cada vez que se escribe algo en `notesField`, el código verifica el contenido. Dependiendo de ciertas palabras clave (`#gtg/`, `#reb - e`, etc.), el código decide qué casillas de verificación marcar o desmarcar, y qué texto agregar o eliminar.


