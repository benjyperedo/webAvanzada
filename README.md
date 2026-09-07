# webAvanzada
lab 1 web avanzada


# Pregunta 1
¿Por qué no se recomienda desarrollar directamente sobre main en este laboratorio?
R: Esto no se recomienda debido a que buscamos trabajar con pull request, lo cual permite que los cambios se validen antes de fusionarlos.

# Pregunta 2
¿Qué problema se evita al utilizar --skip-git al crear el proyecto Angular?
R: Al utilizar --skip-git se evita que el repositorio se clone o se cree un segundo repositorio dentro de  la carpeta .git

# Pregunta 3
¿Qué verifica npm run build en esta etapa del laboratorio?
R: Verifica de forma local que angular compile correctamente y no tenga errores de sintaxis.

# Pregunta 4
¿Qué utilidad tiene revisar git status o git diff --cached antes de realizar un commit?
R: Permite revisar que archivos e informacion serán registrados en el repositorio, para evitar subir elementos no deseados.

# Pregunta 5
¿Qué evento activa el workflow ci.yml?
R: Se activa cuando se crean pull request hacia la rama main

# Pregunta 6
En runs-on: ubuntu-latest, ¿qué representa ubuntu-latest?
R: Representa el sistema operativo del servidor que github levanta en la nube.

# Pregunta 7
Ordene las etapas de validación que ejecuta el job frontend y explique por qué npm ci se ejecuta antes que las pruebas.
R: El orden es obtener codigo, configurar el node.js, instalar dependencias, ejecutar pruebas y construir angular.npm. ci debe ejecutarse antes porque descarga las librerías necesarias para que angular y sus pruebas puedan funcionar.

# Pregunta 8
Después del push, indique qué etapa del pipeline falla y qué ocurre con las etapas siguientes.
R: Falla la etapa ejecutar pruebas, (npm test). Al fallar este paso, la ejecucción se detiene inmediatamente y se cancelan las siguientes etapas.

# Pregunta 9
¿Debería integrarse este Pull Request a main mientras el pipeline está fallando? Justifique.
R: No debería, ya que el código tiene errores comprobados y si se integran se propagará un error.

# Pregunta 10
Clasifique cada elemento como “versionable”, “variable/configuración” o “secreto/no
versionable”: package.json, API_URL pública, AWS_REGION, DB_PASSWORD, API_TOKEN, terraform.tfstate.
R: - package.json: versionable

- API_URL pública: variable/configuración

- AWS_REGION: variable/configuración

- DB_PASSWORD: secreto/no versionable

- API_TOKEN: secreto/no versionable

- terraform.tfstate: secreto/no versionable

# Pregunta 11
¿Por qué una contraseña o token no debe escribirse directamente dentro de ci.yml, cd.yml o un archivo TypeScript?
R: Porque el codigo fuente e historial de commits quedarán expuestos a cualquier persona que tenga el repositorio, comprometiendo la seguridad del sistema.

# Pregunta 12
Si un secreto real fue incluido en un commit y luego se agrega su archivo a .gitignore, ¿queda solucionado el problema? Explique qué acción adicional debe realizarse
R: No queda solucionado, ya que el secreto seguirá visible en el historial de commits anteriores de Git. La acción fundamental y obligatoria es revocar eo invalidar el token/contraseña inmediatamente del sistema que lo generó.

# Pregunta 13
¿Qué diferencia existe entre terraform validate, terraform plan y terraform apply?
R: validate revisa la sintaxis del codigo, plan simula simula y muestra qué cmabios se van a realizar y apply ejecuta los cambios y crea o modifica la estructura.

# Pregunta 14
¿Por qué ci.yml se activa con pull_request y cd.yml se activa con push sobre main?
R: ci.yml se usa para probar y validar el código antes de aceptarlo. cd.yml despliega la aplicación y sólo se ejecuta cuando el código ya fue probado.

# Pregunta 15
¿Qué función cumple Terraform dentro de este flujo de CD?
R: Automatiza la provisión de la infraestructura y la preparación del entorno staging.

# Pregunta 16
¿Por qué el workflow usa ${{ secrets.DEMO_TOKEN }} en lugar de escribir el valor directamente?
R: Para inyectar el valor de forma segura al momento de ejecutar el pipeline, evitando que el secreto quede expuesto.