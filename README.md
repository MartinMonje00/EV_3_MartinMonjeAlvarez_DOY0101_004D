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

## Declaracion uso de Inteligencia Artificial

El uso de inteligencia articifial, en este caso, el uso de google Gemini, fue efectuado dentro de este proyecto con el fin de la resolucion de errores dentro del entorno de escritorio, ya que a diferencia de casos donde normalmente se hace uso de windows como sistema operativo, en este caso posiblemente particular, el ambiente de escritorio es en base al sistema operativo GNU/Linux, lo que permitio que docker funcionase de manera mas nativa dentro de este ambiente, el cual, su distribucion es la de Linux Manjaro, distribucion basada en Arch Linux.
El uso de la inteligencia artificial no se limito a solamente resolver errores con el levantamiento inicial del proyecto con docker, si no que tambien se uso para resolver dudas con respecto al funcionamiento de docker y sus comandos, asi como tambien el uso para obtener sugerencias, y el analisis de errores durante el transcurso de la implementacion de docker dentro del trabajo evaluativo.

## Reflexion personal

A pesar de que todo esto este hecho en base a un proyecto al cual se le hizo un fork para poder trabajar, y de que para este trabajo se haya hecho el uso de Inteligencia Artificial, todo esto me ha servido para aprender la importancia de un pipeline CI/CD bien estructurado dentro de un proyecto. Todo este conocimiento, y el que pueda adquirir a futuro dentro de este curso, me va a ser bastante util al momento de entrar en un ambiente laboral real, donde con todos estos conocimientos de como integrar un pipeline se pueda automatizar las tareas que se hacen al momento del despliegue de un proyecto real, asi como su mantenibilidad por su facilidad de integracion continua, o su despliegue continuo al mento de actualizaciones importantes. A lo que quiero llegar, es que a pesar de que este conocimiento al principio del semestre academico haya sido dificil de procesar, el poder entenderlo y procesarlo de manera correcta me va a ser de bastante utilidad a futuro, sobre todo cuando en el momento de iniciar un proyecto real.
Lo que tambien tengo que agregar, es que, a pesar de que practicamente los archivos Dockerfile que estan en este repositorio son iguales a los que fueron construidos por el profesor, no fue una copia arbitraria del codigo, todo esto fue escrito a mano a partir del codigo ya hecho, al igual que comprendia el codigo que tiene hecho el profesor. Sera una forma extraña de decir copiar al final, pero esta es una de mis formas de estudiar y entender el codigo con el que estoy trabajando.
