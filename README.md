# EV_2_MartinMonjeAlvarez_DOY0101_004D

## Explicacion uso de metodologia Ágil

La idea del repositorio en si es que pueda funcionar con la metodoogia de trabajo gitflow, y la razon del porque es por la naturaleza de los proyectos, requiriendo cambios rapidos y continuos en la rama main, cosa que la metodologia truncada, no permite en muchos casos.

## Adicion de GitHub Actions

La adicion hecha de GitHub Actions es la de que al momento de hacer un Commit o Pull Request a la Branch Main, esta va a ejecutar de forma automatica unos test para asegurar que el codigo de la aplicacion en desarrollo no se rompa en cuanto a codigo al momento de su ejecucion.

## Integración de Docker dentro del repositorio

La integracion de docker dentro de este repositorio es con la intencion de poder hacer la simulacion de un ambiente de integracion continua y despliegue continuo a como lo seria en un ambiente real de produccion. Todo esto se logra gracias a el trabajo de integracion de pipelines de CI/CD, donde no solamente se simulan integraciones y despliegues continuos, si no que tambien se simulan el uso de pruebas previas al despliegue del proyecto de ejemplo.

## Ajustes al pipeline CI/CD con github actions y Docker

Dentro de todo lo que se implemento, github actions, y Docker, la mejor manera de manejar todo esto de manera mas ordenara y simplificada se hace por medio de actions y docker compose, actions para acciones de auto-ejecucion al momento de activar algun trigger por un commit o pull request dentro de github, y docker compose su uso es vital, ya que algunas actividades se pueden automatizar gracias a github actions y docker, las tareas mas pesadas que maneja docker no se deberian de ejecutar manualmente (como seria hacer que se active manualmente un contenedor y despues activar otro contenedor para hacer otra actividad), y para eso esta lo que se le conoceria un orquestador, que en este caso es docker compose, con el cual se puede automatizar el levantamiento de contenedores y sus instrucciones a realizar de manera independiente.

Por lo cual, github actions es necesario para ejecutar pruebas automaticamente al realizar ciertas acciones dentro de github, mientras que, y gracias a github actions, las acciones que debe de hacer docker compose se pueden ejecutar automaticamente por medio de github actions, ya sea pruebas automatizadas, o un despliegue remoto automatizado por medio de este orquestador.

Tambien lo mas importante integrado dentro de los pipelines al hacer commit o pull request dentro de la rama main, es la adicion de test automatizados dentro de estos mismos, los cuales compilan el codigo, lo ejecutan en los test de JaCoCo, y se realiza un analisis de codigo con Sonarqube, con lo que todo lo que se hacia a mano se realiza de mandera automatica e independiente al momento de subir cualquier cosa dentro de la rama main. Ahora, al momento de que pase todos los test correspondientes de JaCoCo (con un porcentaje de exito minimo), la aplicacion ya compilada se guarda como artefacto dentro de los resultados de GitHub Actions, permitiendo de esta manera, el despliegue continuo de un proyecto.

## Declaracion uso de Inteligencia Artificial

El uso de inteligencia articifial, en este caso, el uso de google Gemini, fue efectuado dentro de este proyecto con el fin de la resolucion de errores dentro del entorno de escritorio, ya que a diferencia de casos donde normalmente se hace uso de windows como sistema operativo, en este caso posiblemente particular, el ambiente de escritorio es en base al sistema operativo GNU/Linux, lo que permitio que docker funcionase de manera mas nativa dentro de este ambiente, el cual, su distribucion es la de Linux Manjaro, distribucion basada en Arch Linux.

El uso de la inteligencia artificial no se limito a solamente resolver errores con el levantamiento inicial del proyecto con docker, si no que tambien se uso para resolver dudas con respecto al funcionamiento de docker y sus comandos, asi como tambien el uso para obtener sugerencias, y el analisis de errores durante el transcurso de la implementacion de docker dentro del trabajo evaluativo.

## Reflexion personal experiencia 2

A pesar de que todo esto este hecho en base a un proyecto al cual se le hizo un fork para poder trabajar, y de que para este trabajo se haya hecho el uso de Inteligencia Artificial, todo esto me ha servido para aprender la importancia de un pipeline CI/CD bien estructurado dentro de un proyecto. Todo este conocimiento, y el que pueda adquirir a futuro dentro de este curso, me va a ser bastante util al momento de entrar en un ambiente laboral real, donde con todos estos conocimientos de como integrar un pipeline se pueda automatizar las tareas que se hacen al momento del despliegue de un proyecto real, asi como su mantenibilidad por su facilidad de integracion continua, o su despliegue continuo al mento de actualizaciones importantes. A lo que quiero llegar, es que a pesar de que este conocimiento al principio del semestre academico haya sido dificil de procesar, el poder entenderlo y procesarlo de manera correcta me va a ser de bastante utilidad a futuro, sobre todo cuando en el momento de iniciar un proyecto real.

Lo que tambien tengo que agregar, es que, a pesar de que practicamente los archivos Dockerfile que estan en este repositorio son iguales a los que fueron construidos por el profesor, no fue una copia arbitraria del codigo, todo esto fue escrito a mano a partir del codigo ya hecho, al igual que comprendia el codigo que tiene hecho el profesor. Sera una forma extraña de decir copiar al final, pero esta es una de mis formas de estudiar y entender el codigo con el que estoy trabajando.

Lo mismo aplica para varios archivos dentro del repositorio, que, y reitero, a pesar de que sea casi una copia 1 a 1 del codigo escrito por el profesor, todo esto fue hecho con el fin de la comprension y estudio

En resumen, toda esta experiencia me sirvio para entender la importancia de la Ingenieria DevOps dentro de los proyectos reales, y tambien comprendiendo la utilidad real de estos recursos.

# Integracion de un cluster de Kubernetes -- Tercera evaluacion Ingenieria DevOps

## El proceso de integracion y dependencias

Para lo que fue la tercera parte importante de todo el repositorio, se hizo la integracion del despliegue continuo con el uso de un cluster de Kubernetes, donde estre proceso se realizo de manera local dentro de un computador con el sistema operativo linux para mejor manejo del cluster junto a Docker.

La integracion del cluster fue por medio de la instalacion de los paquetes minikube para crear el cluster kubectl para el manejo del cluster por medio del CLI (El Bash o terminal en este caso en linux), y la instalacion local de istioctl, con el cual se incluye todos los plugins necesarios para el monitoreo de trafico de red y de consumo de recursos dentro del cluster.

La razon de que se necesite el cluster, es para la simulacion de despliegue continuo, o en su defecto, hacer el despliegue continuo de un proyecto junto al monitoreo del mismo proyecto, ademas de que la razon del uso de kubernetes es por la eficiencia de computo en la orquestacion y gestion de aplicaciones contenidas, en comparacion a opciones mas basicas como lo podria ser docker compose.

## Monitoreo con Istio

Al momento de iniciar con el proceso de arranque del cluster de manera local, se le inyecta el servicio de istio junto a los plugins necesarios para todos los dashboards de monitoreo (Este caso siendo Kiali, grafana, y el addon de prometheus para que funcione el monitoreo de los dashboards), donde la informacion que se muestra dentro de los dashboards de kiali y grafana

Kiali: Con este dashboard se puede monitorear el trafico en la red dentro del cluster, en este caso siendo un trafico constante simulado de red dentro del propio cluster. La forma de monitoreo con este dashboard, es por medio de registros, o Logs, o tambien con la posibilidad de un monitoreo por medio de una interfaz grafica a un tiempo real de monitoreo

Grafana: Dentro de este dashboard se realiza el monitoreo de consumo de recursos disponibles dentro del cluster, a como lo puede ser el espacio de almacenamiento disponible, el uso de memoria RAM, y el uso porcentual de CPU (esto incluye ampliamente el cluster, la implementacion de istio, los dashboards incluidos con istio, y los pods donde estan contenidas las aplicaciones). Ademas de que todo esto al ser dentro de un ambiente local, esto es necesario para que no se consuman recursos del computador de manera desmedida.

## Manejo de sobreconsumo de recursos por parte del cluster

Para el momento de que una aplicacion contenida (o pods dentro del ambiente de kubernetes) llegue a consumir de manera desmedida los recursos disponibles, kubernetes mata automaticamente este proceso y levanta una nueva aplicacion contenida.

Todo esto es de manera automatica gracias a las configuraciones de istio y de las propias configuraciones del cluster dentro de los archivos deployment.yaml y service.yaml

## Reflexion personal experiencia 3

Al igual que paso en la experiencia anterior, se hace mencion del uso de la inteligencia artificial, pero todo esto, y al igual que con la experiencia anterior, fue con el fin de entender, comprender y aprender sobre los componentes que se han usado dentro de la experiencia numero 3 del curso Ingenieria DevOps, ya que con las clases se puede aprender gran parte de todo lo que se ha de aplicar dentro del repositorio de trabajo, pero con la inteligencia artificial (y solo para terminar de remarcar su uso dentro de la experiencia), usada en forma de herramienta de arendizaje, pude aprender lo importante del uso y las capacidades del uso del cluster de kubernetes dentro de proyectos reales.

A pesar de que esto haya sido de lo basico que se puede de aprender dentro del curso, esto me abre las puertas a querer aprender sobre el uso extendido de estas herramientas que han enseñado dentro de ingenieria devops, y de ser necesario, o por vocacion propia, por medio de todo lo aprendido con estas 3 experiencias llegar a especializarme dentro de esta area de la informatica.
