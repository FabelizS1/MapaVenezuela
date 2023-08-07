# DataMaps

Este Mapa fue hecho con  el plugin de javascript de Datamaps
https://datamaps.github.io/


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




