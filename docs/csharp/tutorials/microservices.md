---
title: 'Microservicios hospedados en Docker: C#'
description: Aprenda a crear microservicios de ASP.NET Core que se ejecutan en contenedores de Docker.
keywords: .NET, .NET Core, Docker, C#, ASP.NET, microservicios
author: BillWagner
ms.author: wiwagn
ms.date: 02/03/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: csharp
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 6cdc4eb0d0fea93b5210532210ad0c928e35a7a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-hosted-in-docker"></a>Microservicios alojados en Docker

## <a name="introduction"></a>Introducción

En este tutorial se describen las tareas necesarias para compilar e implementar un microservicio de ASP.NET Core en un contenedor de Docker. Durante el transcurso de este tutorial, aprenderá a:

* Generar una aplicación de ASP.NET Core mediante Yeoman
* Crear un entorno de desarrollo de Docker
* Crear una imagen de Docker basada en una imagen existente
* Implementar su servicio en un contenedor de Docker

Por el camino, también verá algunas características del lenguaje C#:

* Cómo convertir objetos de C# en cargas de JSON
* Cómo compilar objetos de transferencia de datos inmutables
* Cómo procesar solicitudes HTTP entrantes y generar la respuesta HTTP
* Cómo trabajar con tipos de valor que aceptan valores null

Puede [ver o descargar la aplicación de ejemplo](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) para este tema. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="why-docker"></a>¿Por qué Docker?

Docker facilita la creación de imágenes de máquina estándar para hospedar los servicios de un centro de datos o en la nube pública. Docker le permite configurar la imagen y replicarla según sea necesario para escalar la instalación de la aplicación.

Todo el código de este tutorial funciona en cualquier entorno .NET Core.
Las tareas adicionales para una instalación de Docker funcionarán para una aplicación de ASP.NET Core. 

## <a name="prerequisites"></a>Requisitos previos
Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).
Puede ejecutar esta aplicación en Windows, Ubuntu Linux, macOS o en un contenedor de Docker. Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

También deberá instalar el motor de Docker. Consulte la [página de instalación de Docker](http://www.docker.com/products/docker) para obtener instrucciones para su plataforma.
Docker puede instalarse en muchas distribuciones de Linux, macOS o Windows. La página mencionada anteriormente contiene secciones para cada una de las instalaciones disponibles.

La instalación de la mayoría de componentes se realiza mediante un administrador de paquetes. Si tiene instalado el administrador de paquetes de node.js `npm`, puede omitir este paso. Si no, instale el archivo de NodeJs más reciente desde [nodejs.org](https://nodejs.org), que instalará el administrador de paquetes de npm. 

En este punto, deberá instalar una serie de herramientas de línea de comandos compatibles con el desarrollo de ASP.NET Core. Las plantillas de línea de comandos usan Yeoman, Bower, Grunt y Gulp. Si las tiene instaladas, genial, si no, escriba lo siguiente en su shell favorito:

`npm install -g yo bower grunt-cli gulp`

La opción `-g` indica que es una instalación global y esas herramientas están disponibles en todo el sistema. (En una instalación local el ámbito del paquete es un único proyecto). Cuando haya instalado las herramientas básicas, debe instalar los generadores de plantillas ASP.NET de Yeoman:

`npm install -g generator-aspnet`

## <a name="create-the-application"></a>Crear la aplicación

Ahora que ha instalado todas las herramientas, cree una nueva aplicación de ASP.NET Core. Para usar el generador de línea de comandos, ejecute el siguiente comando de Yeoman en su shell favorito:

`yo aspnet`

Este comando le pide que seleccione el tipo de aplicación que desea crear. Para este microservicio, desea la aplicación web más sencilla y ligera posible, así que seleccione "Empty Web Application" (Aplicación web vacía). La plantilla le solicita un nombre. Seleccione "WeatherMicroservice". 

La plantilla crea ocho archivos:

* Un archivo .gitignore, personalizado para aplicaciones de ASP.NET Core.
* Un archivo Startup.cs. Este archivo contiene la base de la aplicación.
* Un archivo Program.cs. Este archivo contiene el punto de entrada de la aplicación.
* Un archivo WeatherMicroservice.csproj. Este es el archivo de compilación de la aplicación.
* Un archivo Dockerfile. Este script crea una imagen de Docker para la aplicación.
* Un archivo README.md. Este archivo contiene vínculos a otros recursos de ASP.NET Core.
* Un archivo web.config. Este archivo contiene información de configuración básica.
* Un archivo runtimeconfig.template.json. Este archivo contiene la configuración de depuración usada por los IDE.

Ahora puede ejecutar la aplicación generada por la plantilla. Para ello se usa una serie de herramientas desde la línea de comandos. El comando `dotnet` ejecuta las herramientas necesarias para el desarrollo de .NET. Cada verbo ejecuta un comando diferente.

El primer paso consiste en restaurar todas las dependencias:

```console
dotnet restore
```

La restauración de Dotnet emplea el Administrador de paquetes NuGet para instalar todos los paquetes necesarios en el directorio de la aplicación. También genera un archivo project.json.lock. Este archivo contiene información sobre cada paquete al que se hace referencia. Después de restaurar todas las dependencias, compile la aplicación:

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Una vez compilada, ejecútela desde la línea de comandos:

```console
dotnet run
```

La configuración predeterminada escucha a http://localhost: 5000. Abra un explorador y vaya a esa página. Verá un "¡Hola a todos!". .

### <a name="anatomy-of-an-aspnet-core-application"></a>Anatomía de una aplicación de ASP.NET Core

Ahora que ha creado la aplicación, echemos un vistazo a cómo se implementa esta funcionalidad. Dos de los archivos generados son especialmente interesantes en este momento: project.json y Startup.cs. 

Project.JSON contiene información sobre el proyecto. Los dos nodos con los que trabaja a menudo son "dependencias" y "marcos". El nodo de dependencias muestra todos los paquetes que son necesarios para esta aplicación.
En este momento, este es un nodo pequeño, que solo necesita paquetes que se ejecutan en el servidor web.

El nodo "marcos" especifica las versiones y configuraciones de .NET Framework que ejecutarán esta aplicación.

La aplicación se implementa en Startup.cs. Este archivo contiene la clase de inicio.

Los dos métodos se llaman en la infraestructura de ASP.NET Core para configurar y ejecutar la aplicación. El método `ConfigureServices` describe los servicios que son necesarios para esta aplicación. Va a crear un microservicio de Lean, así que no es necesario configurar ninguna dependencia. El método `Configure` configura los controladores para las solicitudes HTTP entrantes. La plantilla genera un controlador sencillo que responde a cualquier solicitud con el texto "¡Hola a todos!".

## <a name="build-a-microservice"></a>Creación de un microservicio

El servicio que va a crear proporcionará informes meteorológicos desde cualquier lugar del mundo. En una aplicación de producción, se llamaría a algún servicio para recuperar datos meteorológicos. Para nuestro ejemplo, vamos a generar un pronóstico meteorológico aleatorio. 

Hay una serie de tareas que debe realizar para implementar nuestro servicio de información meteorológica aleatorio:

* Analizar la solicitud entrante para leer la latitud y la longitud.
* Generar algunos datos de pronóstico aleatorios.
* Convertir estos datos de pronóstico aleatorios de objetos de C# a paquetes JSON.
* Establecer el encabezado de respuesta para indicar que el servicio devuelve JSON.
* Escribir la respuesta.

Las secciones siguientes le guiarán en cada uno de estos pasos.

### <a name="parsing-the-query-string"></a>Análisis de la cadena de consulta

Para comenzar, analizará la cadena de consulta. El servicio acepta argumentos "lat" y "long" en la cadena de consulta en este formato:

`http://localhost:5000/?lat=-35.55&long=-12.35`  

Todos los cambios que debe realzar se encuentran en la expresión lambda definida como el argumento para `app.Run` en la clase de inicio.

El argumento en la expresión lambda es el elemento `HttpContext` para la solicitud. Una de sus propiedades es el objeto `Request`. El objeto `Request` tiene una propiedad `Query` que contiene un diccionario de todos los valores en la cadena de consulta de la solicitud. La primera adición consiste en encontrar los valores de latitud y longitud:

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

Los valores del diccionario de consulta son de tipo `StringValue`. Ese tipo puede contener una colección de cadenas. Para el servicio de información meteorológica, cada valor es una única cadena. Es por eso que existe la llamada a `FirstOrDefault()` en el código anterior. 

A continuación, debe convertir las cadenas en valores dobles. El método que va a usar para convertir la cadena en un doble es `double.TryParse()`:

```csharp
bool TryParse(string s, out double result);
```

Este método aprovecha parámetros de salida de C# para indicar si la cadena de entrada se puede convertir en un doble. Si la cadena representa un valor doble válido, el método devuelve true y el argumento `result` contiene el valor. Si la cadena no representa un valor doble válido, el método devuelve false.

Puede adaptar dicha API con el uso de un *método de extensión* que devuelve un *valor doble que acepta valores NULL*. Un *tipo de valor que acepta valores NULL* es un tipo que representa algún tipo de valor y también puede contener un valor que falta o un valor NULL. Un tipo que acepta valores NULL se representa mediante la anexión del carácter `?` a la declaración de tipos. 

Los métodos de extensión son métodos que se definen como métodos estáticos, pero al agregar el modificador `this` en el primer parámetro, se pueden llamar como si fueran miembros de esa clase. Los métodos de extensión solo se pueden definir en clases estáticas. Esta es la definición de la clase que contiene el método de extensión para el análisis:

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

La expresión `default(double?)` devuelve el valor predeterminado del tipo `double?`. Este valor predeterminado es el valor NULL (o que falta).

Puede usar este método de extensión para convertir los argumentos de cadena de consulta en el tipo doble:

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

Para probar fácilmente el código de análisis, actualice la respuesta para incluir los valores de los argumentos:

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

En este punto, puede ejecutar la aplicación web y ver si su código de análisis está funcionando. Agregue valores a la solicitud web en un explorador y verá los resultados actualizados.

### <a name="build-a-random-weather-forecast"></a>Creación de un pronóstico meteorológico aleatorio

La siguiente tarea consiste en crear un pronóstico meteorológico aleatorio. Comencemos con un contenedor de datos que contiene los valores que desea para un pronóstico meteorológico:

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

A continuación, cree un constructor que establezca esos valores de forma aleatoria. Este constructor usa los valores de la latitud y la longitud para inicializar el generador de números aleatorios. Esto significa que el pronóstico para la misma ubicación es el mismo. Si cambia los argumentos para la latitud y la longitud, obtendrá un pronóstico diferente (ya que comienza con un valor de inicialización diferente).

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

Ahora puede generar el pronóstico de cinco días en el método de respuesta:

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a>Compile la respuesta JSON.

La tarea final de código en el servidor es convertir la matriz WeatherReport en un paquete JSON y devolverlo al cliente. Comencemos creando el paquete JSON. Agregará el serializador NewtonSoft de JSON a la lista de dependencias. Puede hacerlo mediante la CLI de `dotnet`:

```
dotnet add package Newtonsoft.Json
```

A continuación, puede usar la clase `JsonConvert` para escribir el objeto en una cadena:

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

El código anterior convierte el objeto de pronóstico (una lista de objetos `WeatherForecast`) en un paquete JSON. Después de haber construido el paquete de respuesta, establezca el tipo de contenido en `application/json` y escriba la cadena.

Ahora, la aplicación se ejecuta y devuelve los pronósticos aleatorios.

## <a name="build-a-docker-image"></a>Creación de una imagen de Docker

La tarea final es ejecutar la aplicación en Docker. Vamos a crear un contenedor de Docker que ejecute una imagen de Docker que representa la aplicación.

Una ***imagen de Docker*** es un archivo que define el entorno de ejecución de la aplicación.

Un ***contenedor de Docker*** representa una instancia en ejecución de una imagen de Docker.

Por analogía, puede considerar la *imagen de Docker* como una *clase*y el *contenedor de Docker* como un objeto o una instancia de esa clase.  

El Dockerfile creado por la plantilla de ASP.NET servirá para nuestros propósitos. Repasemos su contenido.

La primera línea especifica la imagen de origen:

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

Docker le permite configurar una imagen de máquina basada en una plantilla de origen. Esto significa que no tiene que suministrar todos los parámetros de máquina cuando se inicia, solo tiene que proporcionar los cambios. Aquí los cambios van a ser incluir nuestra aplicación.

En este primer ejemplo, usaremos la versión `1.1-sdk-msbuild` de la imagen de dotnet. Esta es la manera más fácil de crear un entorno de trabajo de Docker. Esta imagen incluye el tiempo de ejecución de dotnet core y el SDK de dotnet. Como resultado, es más fácil comenzar a trabajar y realizar la compilación, pero la imagen que se crea es más grande.

Las siguientes cinco líneas instalan y compilan su aplicación:

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

El archivo de proyecto se copia del directorio actual a la máquina virtual de Docker y se restauran todos los paquetes. El uso de la CLI de dotnet significa que la imagen de Docker debe incluir el SDK de .NET Core. Luego, se copia el resto de la aplicación y el comando de publicación de dotnet compila y empaqueta la aplicación.

La última línea del archivo ejecuta la aplicación:

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

Se hace referencia a este puerto configurado en el argumento `--server.urls` para `dotnet` en la última línea del Dockerfile. El comando `ENTRYPOINT` informa a Docker de qué opciones de comando y de línea de comandos inician el servicio. 

## <a name="building-and-running-the-image-in-a-container"></a>Compilación y ejecución de la imagen en un contenedor

Vamos a compilar una imagen y ejecutar el servicio dentro de un contenedor de Docker. No desea copiar todos los archivos de su directorio local en la imagen. En su lugar, va a compilar la aplicación en el contenedor. Creará un archivo `.dockerignore` para especificar los directorios que no se copian en la imagen. No desea copiar ninguno de los recursos de compilación. Especifique los directorios de compilación y publicación en el archivo `.dockerignore`:

```
bin/*
obj/*
out/*
```

Compilará la imagen mediante el comando de compilación de Docker. Ejecute el siguiente comando desde el directorio que contiene el código.

```console
docker build -t weather-microservice .
```

Este comando compila la imagen de contenedor en función de toda la información del Dockerfile. El argumento `-t` proporciona una etiqueta, o nombre, para esta imagen de contenedor. En la línea de comandos anterior, la etiqueta usada para el contenedor de Docker es `weather-microservice`. Cuando termina este comando, tendrá un contenedor listo para ejecutar el nuevo servicio. 

Ejecute el siguiente comando para iniciar el contenedor y el servicio:

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

La opción `-d` implica ejecutar el contenedor desasociado del terminal actual. Esto significa que no verá la salida del comando en el terminal. La opción `-p` indica la asignación de puertos entre el servicio y el host. Aquí dice que cualquier solicitud entrante en el puerto 80 se debe reenviar al puerto 5000 en el contenedor. El uso de 5000 coincide con el puerto en el que escucha su servicio desde los argumentos de línea de comandos especificados en el Dockerfile anterior. El argumento `--name` nombra el contenedor en ejecución. Es un nombre adecuado que puede usar para trabajar con ese contenedor. 

Para ver si la imagen se ejecuta, compruebe el comando:

```console
docker ps
```

Si el contenedor se está ejecutando, verá una línea que lo indica en los procesos en ejecución. (Puede que sea la única).

Para probar el servicio, abra un explorador y vaya a localhost, luego especifique la latitud y la longitud:

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a>Asociación de un contenedor en ejecución

Cuando ejecutó su servicio en una ventana de comandos, ha podido ver información de diagnóstico impresa para cada solicitud. Cuando el contenedor se ejecuta en modo de desconexión, no puede ver esa información. El comando attach de Docker le permite conectarse a un contenedor en ejecución para ver la información de registro.  Ejecute este comando desde una ventana de comandos:

```console
docker attach --sig-proxy=false hello-docker
```

El argumento `--sig-proxy=false` significa que los comandos `Ctrl-C` no se envían al proceso del contenedor, sino que detienen el comando `docker attach`. El argumento final es el nombre asignado al contenedor en el comando `docker run`. 

> [!NOTE]
> También puede usar el id. de contenedor asignado a Docker para hacer referencia a cualquier contenedor. Si no especifica un nombre para su contenedor en `docker run`, debe usar el id. de contenedor.

Abra un explorador y vaya a su servicio. Verá los mensajes de diagnóstico en las ventanas de comandos desde el contenedor en ejecución conectado.

Presione `Ctrl-C` para detener el proceso de conexión.

Cuando haya terminado de trabajar con el contenedor, puede detenerlo:

```console
docker stop hello-docker
```

El contenedor y la imagen siguen estando disponibles para que los reinicie.  Si desea quitar el contenedor de la máquina, use este comando:

```console
docker rm hello-docker
```

Si desea quitar imágenes no usadas de la máquina, utilice este comando:

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a>Conclusión 

En este tutorial, ha creado un microservicio de ASP.NET Core y ha agregado unas cuantas características sencillas.

Ha compilado una imagen de un contenedor de Docker para ese servicio y ha ejecutado ese contenedor en su máquina. Ha conectado una ventana de terminal al servicio y ha visto los mensajes de diagnóstico de su servicio.

Por el camino, ha visto varias características del lenguaje C# en acción.
