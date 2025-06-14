TUTORIAL
Cómo crear una Loyalty Card con Botón para Cafetería (HTML y CSS)
¿Alguna vez te has preguntado cómo se construyen esas tarjetas de fidelidad interactivas que ves en tus cafeterías favoritas? En este tutorial, mostraré el paso a paso para crear tu propia "Loyalty Card" (tarjeta de fidelidad) con un diseño moderno, utilizando HTML para la estructura y CSS con Flexbox para el estilizado y la responsividad. 
1.Esqueleto HTML
Cree una muestra de card de cafetería para canjear puntos junto con un botón de crear card. En el HTML utilicé, principalmente, divs y p. 
Los divs se usan como contenedores para agrupar elementos y aplicar estilos en CSS. Dentro de la loyalty-card, el div con el diseño de la tarjeta se desglosa jerárquicamente en más divs, como: card-header, profile-circle, card-info, card-name, card-id, card-level, card-points. Cada div tiene su clase correspondiente.
También, cree un button con div (<button class="create-card-button">crear card</button>), Ambos tanto la card como el button están dentro de una misma section. Cada cual con su div correspondiente. Los p se usan para párrafos de texto, como el mensaje inicial y los datos de la tarjeta.

```html
<section class="loyalty-card-section">
        <div class="card-container">
            <div class="loyalty-card">
                <div class="card-header">
                    <div class="profile-circle"></div>
                    <div class="card-info">
                        <p class="card-name">Italian Coffee Loyalty</p>
                        <p class="card-id">ID: 1234 5678 9012</p>
                        <p class="card-level">Miembro Premium</p>
                </div>
            </div>
            <div class="card-points">
                <p>Puntos Acumulados: <span>125</span></p>
            </div>
            </div>
        <button class="create-card-button">crear card</button>
        </div>
        </section>
```

2.Estilos CSS 
En el CSS, use flexbox para centrar la tarjeta y para su diseño interno. Como he mencionado en lineas anteriores, recalco nuevamente que dividí la tarjeta en diferentes divs que usaron display: flex para lograr el layout deseado.
El display: flex se aplica a los contenedores (.loyalty-card-section, .card-container, .loyalty-card, .card-header) para organizar a sus hijos directos. Los hijos indirectos son los elementos de texto o las imágenes individuales (como los párrafos, las imágenes de los regalos o el span de los puntos), adquieren un estilo de sus propias propiedades de texto, tamaño y color, y su posición es controlado por el contenedor flex del hijo directo.

```css
/*Seccion tarjeta de fidelidad
se estilizan la tarjeta y el boton de crear card
usamos flexbox para centrar la tarjeta y para su diseño interno
*/


.loyalty-card-section {
    display: flex; /* para convertirla en un contenedor flex*/
    justify-content: center; /*para centrar horizontal y verticalmente todo el contenido de la sección, tarjeta y boton*/
    align-items: center;  /*para centrar horizontal y verticalmente todo el contenido de la sección, tarjeta y boton*/
    padding: 50px 20px; /* Espaciado interno */
    background-color: #f5f5f5; /* Fondo suave para esta sección */
}


.card-container {
    display: flex; /* para convertirla en un contenedor flex*/
    flex-direction: column; /* Apila la tarjeta y el botón verticalmente, uno sobre el otro */
    align-items: center; /* Centra horizontalmente */
    gap: 20px; /*Espacio entre la tarjeta y el botón*/
}


.loyalty-card {
    width: 350px; /*ancho tipico de tarjeta*/
    height: auto; /*alto de tarjeta de credito simulada*/
    background: linear-gradient(135deg,#4A2B1A 0%, #8B4513 100%); /* Degradado de colores café */
    border-radius: 15px; /* Bordes redondeados */
    box-shadow: 0 10px 20px rgba (0,0,0,0.2);  /* Sombra para dar profundidad */
    padding: 25px; /* Espaciado interno para el contenido de la tarjeta */
    color: white; /* Color de texto blanco para contrastar con el fondo */
    display: flex; /* Flexbox para el contenido interno de la tarjeta */
    flex-direction: column; /*aplica el header y los puntos en vertical*/
    justify-content: space-between; /* Espacio entre header y puntos */
}


.card-header {
    display: flex; /*flexbox para el circulo y la info*/
    align-items: center; /* Centra los elementos verticalmente */
    gap: 20px; /*espacio entre el circulo y el txt*/
    margin-bottom: 20px;
}


.profile-circle {
    width: 70px; /* Ancho del círculo */
    height: 70px; /* Alto del círculo (lo mismo que el ancho para que sea un círculo) */
    border-radius: 50%; /* Hace que el div sea un círculo */
    border: 3px solid #fff; /* Borde blanco para el círculo */
    background-color: rgba(255, 255, 255, 0.2); /* Fondo semi-transparente */
    background-image: url('AuroraDawn.jpg');
    background-size: cover; /* Escala la imagen para que cubra todo el círculo */
    background-position: center; /* Centra la imagen dentro del círculo */
    background-repeat: no-repeat; /* Evita que la imagen se repita */
}


.card-info p {
    margin: 0; /*elimina margenes por defecto de los parrafos*/
}


.card-name {
    font-size: 1.4em;m/* Tamaño de fuente para el nombre de la tarjeta */
    font-weight: bold; /* Negrita */
    margin-bottom: 5px; /* Pequeño margen inferior */
}


.card-id {
    font-family: 'Courier New', monospace; /* Fuente monoespaciada para el ID */
    font-size: 1.1em; /* Pequeño margen inferior */
    opacity: 0.9; /* Ligeramente transparente */
}


.card-level {
    font-size: 0.9em; /* Tamaño de fuente más pequeño para el nivel */
    font-style: italic;/* Cursiva */
    opacity: 0.8; /* Más transparente */
}


.card-points {
    text-align: right; /* Alinea los puntos a la derecha */
    font-size: 1.3em; /* Tamaño de fuente para los puntos */
    font-weight: bold;  /* Negrita */
}


.card-points span {
    color: #FFD700; /* Color oro para los puntos */
}


.create-card-button {
    background-color: #8B4513; /* color del fondo del boton Marrón del botón */
    color: white; /*color de texto de  boton*/
    padding: 15px 30px; /*espacio interno del boton*/
    border: none; /*sin borde*/
    border-radius: 8px; /*bordes redondeados*/
    font-size: 1.2em; /*tamaño de la letra del boton*/
    cursor: pointer; /* Cambia al pasar por encima */
    transition: background-color 0.3s ease, transform 0.2s ease; /* Transiciones suaves */
}


.create-card-button:hover {
    background-color: #6A340F; /* Color de fondo más oscuro al pasar el ratón */
    transform: translateY(-2px); /* Efecto al pasar el ratón */
}
```

3.Modelo de Caja Global (box-sizing: border-box;)
Por último, quiero mencionar que existen beneficios al aplicar un modelo de caja global con box-sizing: border-box; desde el principio:
Diseño más intuitivos y predecibles
Facilita el diseño responsivo
Evita el desbordamiento 
Consistencia entre diferentes navegadores

```css
/* Modelo de Caja Global */
/* Esto asegura que el padding y el border se incluyan dentro del width/height del elemento. 
Facilita mucho el cálculo de tamaños y el diseño responsivo.
*/
*, *::before, *::after {
    box-sizing: border-box; /* Incluye padding y border en el tamaño total del elemento */
}
```



