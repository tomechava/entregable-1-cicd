# entregable-1-cicd
Primer entregable del curso de CI/CD

## Integrantes

- Tomas Echavarria | github: tomechava

## Preguntas

1. ¿Qué eventos configuraste para disparar tu workflow y por qué?

--> on:push para que al pushear un commit el action se dispare automaticamente, de forma que se ejecute inmediatamente se suban los nuevos cambios. on:workflow_dispatch para poder ejecutar el action manualmente segun sea necesario.

2. ¿Qué sistema operativo utiliza el runner ubuntu-latest y por qué puede ejecutar tu workflow aunque tu computadora sea Windows o macOS? ¿Qué relación tiene el runner con el shell de los pasos run?

--> Utiliza Linux 7.0.0-1017-azure que es lo mismo que ubuntu-latest que fue configurado como el runner del job. El workflow puede ejecutarse en linux ya que no corre en mi maquina local, corre como servicio prestado por github dentro de su plataforma con ese sistema operativo. El runner al ser linux determina que los comandos shell que ejecutamos en los pasos run sean comandos de linux.

3. Menciona al menos 3 acciones pre-construidas del Marketplace de GitHub Actions no mencionadas en este material. Excluye actions/checkout, actions/setup-python, actions/upload-artifact y aws-actions/configure-aws-credentials, aunque alguna solo aparezca como ejemplo conceptual. Describe qué hacen y para qué sirven.

- https://github.com/marketplace/actions/super-linter es una coleccion de linters y analizadores de codigo para validar y corregir codigo fuente, de forma que quede bien formateado y sin errores de sintaxis siguiendo buenas practicas.

- https://github.com/marketplace/actions/setup-node-js-environment es un actions para descargar y cachear distribuciones de Node.js y añadirlas a las variables de entorno, sirve para facilitar la configuracion y versionamiento al utilizar Node.js dentro de un repositorio.

- https://github.com/marketplace/actions/create-pull-request es un actions que permite que al realizar cambios en steps de un workflow, estos cambios persistan para steps siguientes. Estos cambios se les hace commit a una nueva rama y se suben dentro de un Pull Request.

4. ¿Qué es un secreto en GitHub Actions y para qué se usa? ¿Cómo lo usarías en tu workflow?

--> Es un token o llave que permite autorizar ciertas acciones. Se utiliza para limitar o expandir las acciones permitidas para un workflow especifico.

5. Reflexiona sobre el uso de GitHub Actions en tu flujo de trabajo diario. ¿Qué tareas automatizarías? ¿Por qué?

--> Personalmente utilizo gh actions para automatizar suites de testing, linting de codigo y para hacer cd hacia instancias de ec2, de modo que al realizar cambios dentro de mi repositorio el repositorio clonado en la ec2 haga pull de los cambios automaticamente para tener la ultima version del codigo. Esto me evita tener que conectarme a la instancia y hacer pull manualmente cada vez que subo un cambio.


## Enlace de ejecución exitosa del workflow: https://github.com/tomechava/entregable-1-cicd/actions/runs/42380678973 
