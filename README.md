# Trabajo de Fin De Grado: Desarollo de un sistema de pruebas con Node.js para una APIRest externa de servicios blockchain

## Instalación 

1. Instalación de la última versión estable del editor de código Visual Studio Code desde su página oficial, dependiendo del sistema operativo de su dispositivo: https://code.visualstudio.com/ 

 

2. Instalación de Node.js y Node Package Manager, dos opciones:

    a. Mediante la página oficial https://nodejs.org/es/download/:
 

    b.	Mediante el terminal de VS Code:
```
sudo apt-get install nodejs 
sudo apt-get instal npm
```

3.	Crear el directorio y clonar el proyecto en él:
```
cd ~/APItesting 
git clone https://github.com/irenegl3/APItesting
```

4.	Instalar las dependencias del proyecto definidas en el package.json:
```
npm install
```

Una vez se ha realizado el proceso de instalación y se tiene acceso a las distintas carpetas del proyecto, se procede a explicar como ejecutar las diferentes pruebas: 
Primeramente, se configura la URL y clave de la API, en el fichero config.js:
```
var host = 'https://test.api.nodalblock.com';
var apiKey = "";
```
## Ejecución de las pruebas

#### SCRIPTS DE PETICIONES
```
node tests/<directorio>/<fichero js>
```
Donde <directorio> puede ser digitalid, documents, contracts, hash o json, y <fichero js> cualquiera de los ficheros de formato JS de cada carpeta.

#### PRUEBAS DE FUNCIONALIDAD
```
npm run mocha functionalityTests/<directorio>/<fichero js>
```

Donde <directorio> puede ser digitalid, documents, contracts, hash o json, y <fichero js> el fichero de tipo mocha_<servicio>.js de cada carpeta.

#### PRUEBAS DE CARGA
```
npm run artillery reports_load/<fichero json del informe> loadTests/<fichero yml>
```
Donde <fichero json del informe> es el nombre que se quiera dar al report o informe de los resultados de la prueba, y <fichero yml> el fichero de tipo <número de escenario>.yml de cada carpeta que contiene cada prueba de carga del escenario indicado.
Para obtener los resultados en un HTML:
```
npm run draw reports_load/<fichero json del informe>
```

Donde <fichero json del informe> es el nombre dado anteriormente al informe de los resultados de la prueba.
Para modificar la URL y la clave de API, es necesario modificar dicho campo en el fichero YAML.

#### PRUEBAS DE ESTRÉS
```
npm run artillery reports_stress/<fichero json del informe> stressTests/<fichero yml>
```

Donde <fichero json del informe> es el nombre que se quiera dar al report o informe de los resultados de la prueba, y <fichero yml> el fichero de tipo <número de escenario>.yml de cada carpeta que contiene cada prueba de carga del escenario indicado.
Para obtener los resultados en un HTML:
```
npm run draw reports_stress/<fichero json del informe>
```

Donde <fichero json del informe> es el nombre dado anteriormente al informe de los resultados de la prueba.
Para modificar la URL y la clave de API, es necesario modificar dicho campo en el fichero YAML.

#### PRUEBAS DE ESTABILIDAD
```
npm run artillery reports_stability/<fichero json del informe> stabilityTests/<fichero yml>
```

Donde <fichero json del informe> es el nombre que se quiera dar al report o informe de los resultados de la prueba, y <fichero yml> el fichero de tipo <número de escenario>.yml de cada carpeta que contiene cada prueba de carga del escenario indicado.
Para obtener los resultados en un HTML:
```
npm run draw reports_stability/<fichero json del informe>
```
Donde <fichero json del informe> es el nombre dado anteriormente al informe de los resultados de la prueba.
Para modificar la URL y la clave de API, es necesario modificar dicho campo en el fichero YAML.
