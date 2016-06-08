**INTEGRACIÓN CONTINUA: JENKINS, GITHUB, MSBUILD Y VISUAL STUDIO COMMUNITY 2015**

**La integración continua** es una buena práctica de desarrollo de Software. Consiste en que todos los involucrados en el desarrollo de software integren frecuentemente su trabajo y con la compilación y ejecución de pruebas se puedan detectar errores tan rápido como sea posible, y así poder corregirlos. Esta práctica se apoya en el **Versionamiento continúo** en donde solamente se almacena nuestro trabajo llevando una bitácora de los cambios realizado y llevando registro de la anotaciones de cada cambio.

**GitHub:** es un entorno de desarrollo colaborativo para almacenar proyectos de Software en la nube, utiliza el sistema de Versionamiento Git.

**Jenkins:** Es un servidor de integración continua, es de código abierto, Jenkins funciona a base de tareas donde se pueden administrar lo que se hará en un build, como programar cada cuanto tiempo revise nuestro repositorio de Versionamiento o que haga un despliegue a otro servidor, etc.

**Msbuild:** Es una herramienta de construcción de código Microsoft y Visual Studio; Visual Studio depende me Msbuild pero Msbuild no depende de Visual Studio para construir el código. https://en.wikipedia.org/wiki/MSBuild

**Visual Studio Community 2015:** Es la versión más reciente de Visual Studio un completo entorno de desarrollo para crear aplicaciones Windows, iOS y Android así como aplicaciones Web.

**Necesitas:**

Un servidor en donde se instala Jenkins y construirán las soluciones.

Una cuenta en GitHub

Un entorno de desarrollo en este caso Visual Studio

Un servidor de despliegue

**PASOS:**

1.  GITHUB

    1.  Crear una cuenta GitHub llenando los campos necesarios.

> <img src="./media/image1.png" width="325" height="142" />
>
> [*https://github.com*](https://github.com)

1.  Descargar GitHub for Desktop, nos permite trabajar con GitHub desde nuestro escritorio. No es necesario pero podría ser útil para administrar y crear nuevos repositorios. Se puede descargar desde este enlace, y su instalación es muy sencilla. [*https://desktop.github.com*](https://desktop.github.com)

> <img src="./media/image2.png" width="238" height="133" />

1.  VISUAL STUDIO COMMUNITY 2015

    1.  Descargar Visual Studio Community 2015 [*https://www.visualstudio.com/en-us/products/vs-2015-product-editions.aspx*](https://www.visualstudio.com/en-us/products/vs-2015-product-editions.aspx)

        1.  Instalar Visual Studio Community 2015, seleccionar las opciones para instalar los complementos de GitHub.

> <img src="./media/image3.png" width="143" height="151" /><img src="./media/image4.png" width="192" height="58" />

1.  Enlazar Visual Studio con GitHub

    1.  Primero vamos crear un nuevo repositorio en GitHub, el enlace será el mismo donde nos registramos. Ingresamos con nuestros datos y ahí se nos muestra la opción para crear el nuevo repositorio.

<img src="./media/image5.png" width="146" height="169" /><img src="./media/image6.png" width="140" height="140" />

> <img src="./media/image7.png" width="222" height="160" />Colocamos el nombre que le queremos dar a nuestro nuevo repositorio, se nos muestran la opciones para colocar nuestro repositorio como público o privado; lo dejaremos en público. Copiaremos la dirección que ahí nos aparece porque es la que utilizaremos para que Visual Studio se comunique con GitHub.
>
> <img src="./media/image8.png" width="259" height="217" />

1.  Abrimos Visual Studio y en la pestaña Team Explorer que ahí nos aparece, en la sección Local Git Repositories seleccionamos la opción Clone y colocamos la dirección del repositorio creado en GitHub. De nuevo damos clic en Clone y luego se nos mostrara un mensaje que nuestro repositorio ha sido clonado con éxito.

<img src="./media/image9.png" width="348" height="54" /><img src="./media/image10.png" width="185" height="224" />

1.  Para crear un nuevo proyecto dentro de nuestro repositorio

    1.  Damos doble clic en nuestro repositorio clonado y luego seleccionamos la opción New para crear nuevo proyecto. En este caso seleccione un formulario solo para mostrar. Hacemos clic en ok, y podemos agregar los cambios que queramos.

<img src="./media/image11.png" width="195" height="181" /> <img src="./media/image12.png" width="353" height="217" />

1.  Para enviar los cambios al repositorio en GitHub

    1.  En la pestaña de Team Explorer en la opción Change se mostraran todos los cambios que realicemos en nuestro proyecto.

> <img src="./media/image13.png" width="229" height="67" />
>
> Se indicara que debemos escribir un comentario antes de poder enviar los cambios al repositorio en GitHub. Puede ser cualquier comentario que indique cuales fueron los cambios realizados. Luego en la pestaña que aparece daremos clic en la opción Commit All and Push.
>
> <img src="./media/image14.png" width="211" height="227" />
>
> Y se indicara que los cambios fueron enviados con éxito a nuestro repositorio. Y en GitHub se mostrar los cambios enviados.

<img src="./media/image15.png" width="202" height="40" /> <img src="./media/image16.png" width="335" height="179" />

1.  JENKINS

    1.  Descargar Jenkins, en este caso se instalara Jenkins en una Maquinan Virtual con sistema operativo Windows Server 2012, por lo que la versión que seleccionamos la opción de Windows de Jenkins. [*https://jenkins.io*](https://jenkins.io)

> <img src="./media/image17.png" width="293" height="214" />

1.  Instalar Jenkins: una vez descargado el archivo se debe descomprimir y ejecutar el asistente de instalación

<img src="./media/image18.png" width="239" height="185" /><img src="./media/image19.png" width="236" height="187" /><img src="./media/image20.png" width="122" height="41" />

1.  Abrir Jenkins

    1.  Jenkins corre el puerto 8080, en este caso como es un servidor Windows debe de estar habilitado el IIS (Internet Information System). Aquí podrás ver como configurarlo: [*https://msdn.microsoft.com/es-es/library/ms181052(VS.80).aspx*](https://msdn.microsoft.com/es-es/library/ms181052(VS.80).aspx)

    2.  Para acceder a Jenkins solo debemos escribir en cualquier navegador la dirección del IIS en este caso [*http://localhost:8080*](http://localhost:8080)

    3.  Se abrirá una página de Login donde nos pedirá los datos para iniciar sesión o crear un nuevo usuario si aún no tenemos uno.

> <img src="./media/image21.png" width="401" height="185" />

1.  Configurar Jenkins:

    1.  <img src="./media/image22.png" width="100" height="129" /><img src="./media/image23.png" width="359" height="88" />Lo primero será agregar una credencial a Jenkins, esta nos servirá para dar permisos a configuraciones posteriores. Ingresamos los datos que se nos piden y damos clic en OK.
        > <img src="./media/image24.png" width="328" height="67" />

<img src="./media/image25.png" width="589" height="126" />

1.  Luego descargaremos los Plugins necesario para que se comunique ocn Github. En panel de control damos clic en Manage Jenkins y seleccionamos Manage Plugins.

> <img src="./media/image26.png" width="150" height="31" /> <img src="./media/image27.png" width="422" height="41" />

1.  Seleccionamos y descargamos lo Plugins, en la pestaña Available encontramos los que estén disponibles para la descarga. Seleccionar cualquiera de la opciones para descrga e instalación.

<img src="./media/image28.png" width="294" height="150" />

1.  Crear una nueva tarea para construir la solución.

2.  Configurar el nuevo Job para que se comunique con GitHub

<!-- -->

1.  MSBUILD

    1.  Descargar Pluggin de Msbuild desde Jenkins para compilar la solución en el servidor

    2.  Descarga e instalar Msbuild en el servidor

        1.  Tener en cuenta la ruta en donde se instala

    3.  Configura de Jenkins para que trabaje con Msbuild

        1.  Asegurarse de que este agregada en la variable de entorno la dirección del servidor donde se instaló Msbuild

    4.  Configurar el Job de nuestro proyecto para que trabaje con Msbuild

2.  DEPLOY

    1.  Descargar los Pluggins necesarios para que Jenkins haga el despliegue automático.

    2.  Configurar Jenkins para con los datos del servidor de Despliegue

    3.  Configurar el Job con los datos del servidor para que haga el despliegue
