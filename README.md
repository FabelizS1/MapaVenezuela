# DataMaps

Este Mapa fue hecho con  el plugin de javascript de Datamaps
https://datamaps.github.io/


# Autor
Fabeliz Irene Alvarez Salazar


# Mapa de Venezuela

Este es el mapa de Venezuela con todos sus estados. Tiene una breve descripcion cada uno de ellos.


# Como Usarlo

Hacer clic en el boton de Code y descargar el archivo zip o clonar el proyecto.

No es necesario agregar o descargar otro componente.


# HTML

Se agrego al archivo mapa.html lo siguiente:


```bash

    <div class="alignMap">
        <div id="venezuela" style="position: relative; width: 1000px; height: 640px; top: 0;">
        </div>
    </div>

```


# CSS

Se agrego al archivo mapa.html para actualizar las letras lo siguiente:


```bash

        .letrasAzules {
            color:#101aa1;
        }
        
        .LetraTitulo1{
            display: inline;
            color:yellow
        }

        .LetraTitulo2{
            display: inline;
            color:#101aa1
        }

        .LetraTitulo3{
            display: inline;
            color:red
        }

        .letrasBold {
            font-weight: bold;
        }

        .letras {
            font-weight: 0;
        }

        .alignMap {
            display:flex;
            justify-content: center; 
            align-items: center;
            width: 100%;
        }

        .titulos {
            position:relative;
            top: -600px;
        }

```


# Javascript

Se agrego al archivo mapa.html para actualizar el color de fondo, las coordenadas geograficas de Venezuela y la dataurl lo siguiente:


```bash

    var bubble_map = new Datamap({
        element: document.getElementById('venezuela'),
        scope: 'venezuela',
        geographyConfig: {
            popupOnHover: true,
            highlightOnHover: true,
            borderColor: '#022D36',
            borderWidth: 0.5,
            dataUrl: 'https://localhost/fiastecnologia'
            //dataJson: topoJsonData
        },
        fills: {
            'MAJOR': '#306596',
            'MEDIUM': '#0fa0fa',
            'MINOR': '#101aa1',
            defaultFill: '#03AC13'
        },
        data: {
            //'BO': { fillKey: 'MINOR' },
            'DF': { fillKey: 'MINOR' }
        },
        setProjection: function (element) {
            var projection = d3.geo.mercator()
                .center([-65.9718, 8.156421]) // always in [East Latitude, North Longitude]
                .scale(2500)
                .translate([element.offsetWidth / 2, element.offsetHeight / 2]);

            var path = d3.geo.path().projection(projection);
            return { path: path, projection: projection };
        }
    });


```




# Archivo Creado

Se creo el archivo de venezuela.topo  para mostrar la informacion de los estados


```bash

const mapaInfo2 = `{"type":"Topology","objects":{"venezuela":{"type":"GeometryCollection","geometries":[{"type":"MultiPolygon","properties":{"name":null},"id":"-99","arcs":[[[0]],[[1]],[[2]],[[3]],[[4]],[[5]],[[6]],[[7]],[[8]],[[9]],[[10]],[[11]],[[12]],[[13]],[[14]],[[15]],[[16]],[[17]],[[18]],[[19]],[[20]],[[21]],[[22]],[[23]],[[24]],[[25]],[[26]],[[27]],[[28]],[[29]],[[30]],[[31]],[[32]],[[33]]]},{"type":"Polygon","properties":{"name":"<h1 class='letrasAzules'><img src='./img/bandera falcon.png' width='80px' height='50px'/><img src='./img/Escudo falcon.png' width='50px' height='50px'/>Falc&oacute;n</h1> <br/> Capital: Coro<br/>Fundacion: Juan de Ampies en 1527<br/>Superficie: 24.800 Km2<br/>Region: Occidente<br/>Rios Principales: Maticora y Tocuyo<br/>Relieve: Cerro Santa Ana y Sierra de San Luis"},"id":"FA","arcs":[[34,35,36,37]]},{"type":"Polygon","properties":{"name":"<h1 class='letrasAzules'><img src='./img/bandera Apure.png' width='80px' height='50px'/><img src='./img/Escudo apure.jpg' width='50px' height='50px'/>Apure</h1> <br/> Capital: San Fernando de Apure<br/>Fundacion: En 1788<br/>Superficie: 76.500 Km2<br/>Region: Los Llanos<br/>Hidrografia: Rio Apure, Rio Arauca, Ca&ntilde;o Orichuna, Capanaparo<br/>Cinaruco, Cunaviche, Matiyure y Meta"},"id":"AP","arcs":[[38,39,40,41,42]]},{"type":"Polygon","properties":{"name":"<h1 class='letrasAzules'><img src='./img/bandera barinas.jpg' width='80px' height='50px'/><img src='./img/Escudo barinas.png' width='50px' height='50px'/>Barinas</h1> <br/> Capital: Barinas<br/>Fundacion: Juan Andres Valera en 1576<br/>Superficie: 35.200 Km2<br/>Region: Los Llanos<br/>Rios Principales: Apure, Canagua, Guanare<br/>Santo Domingo, Masparro y Mena<br/>"},"id":"BA","arcs":[[43,44,45,-43,46,47,48]]},{"type":"Polygon","properties":{"name":"<h1 class='letrasAzules'><img src='./img/bandera merida.png' width='80px' height='50px'/><img src='./img/Escudo merida.png' width='50px' height='50px'/>Merida</h1> <br/> Capital: Merida<br/>Fundacion: Juan Rodriguez Suarez en 1558<br/>Superficie: 11.300 Km2<br/>Region: Los Andes<br/>

```


![Mapa Venezuela](https://github.com/FabelizS1/MapaVenezuela/assets/137422926/0bebae1e-89f9-4821-8bdf-99167f981bac)







