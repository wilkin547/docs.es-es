---
title: 'Microservicios hospedados en Docker: C#'
description: Aprenda a crear microservicios de ASP.NET Core que se ejecutan en contenedores de Docker.
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: b043b0109bcf8a67867d2c73a5ab22e43a4963cf
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208095"
---
# <a name="microservices-hosted-in-docker"></a>Microservicios alojados en Docker

En este tutorial se describen las tareas necesarias para compilar e implementar un microservicio de ASP.NET Core en un contenedor de Docker. Durante el transcurso de este tutorial, aprenderá a:

* Generar una aplicación de ASP.NET Core.
* Crear un entorno de desarrollo de Docker.
* Crear una imagen de Docker basada en una imagen existente
* Implementar su servicio en un contenedor de Docker

Por el camino, también verá algunas características del lenguaje C#:

* Cómo convertir objetos de C# en cargas de JSON
* Cómo compilar objetos de transferencia de datos inmutables.
* Cómo procesar solicitudes HTTP entrantes y generar la respuesta HTTP.
* Cómo trabajar con tipos de valor que aceptan valores null.

Puede [ver o descargar la aplicación de ejemplo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) para este tema. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="why-docker"></a>¿Por qué Docker?

Docker facilita la creación de imágenes de máquina estándar para hospedar los servicios de un centro de datos o en la nube pública. Docker le permite configurar la imagen y replicarla según sea necesario para escalar la instalación de la aplicación.

Todo el código de este tutorial funciona en cualquier entorno .NET Core.
Las tareas adicionales para una instalación de Docker funcionarán para una aplicación de ASP.NET Core. 

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).
Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.
Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

También deberá instalar el motor de Docker. Consulte la [página de instalación de Docker](http://www.docker.com/products/docker) para obtener instrucciones para su plataforma.
Docker puede instalarse en muchas distribuciones de Linux, macOS o Windows. La página mencionada anteriormente contiene secciones para cada una de las instalaciones disponibles.

## <a name="create-the-application"></a>Crear la aplicación

Ahora que ha instalado todas las herramientas, cree una nueva aplicación de ASP.NET Core. Para ello, cree un directorio denominado "WeatherMicroservice" y ejecute el siguiente comando en ese directorio en el shell de su preferencia:

```console
dotnet new web
```

El comando `dotnet` ejecuta las herramientas necesarias para el desarrollo de .NET. Cada verbo ejecuta un comando diferente.

El comando `dotnet new` se usa para crear proyectos de .NET Core.

Para este microservicio, queremos la aplicación web más sencilla y más ligera posible, por lo que usamos la plantilla "ASP.NET Core vacío", especificando su nombre corto, `web`.

La plantilla crea cuatro archivos:

* Un archivo Startup.cs. Este archivo contiene la base de la aplicación.
* Un archivo Program.cs. Este archivo contiene el punto de entrada de la aplicación.
* Un archivo WeatherMicroservice.csproj. Este es el archivo de compilación de la aplicación.
* Un archivo Properties/launchSettings.json. Este archivo contiene la configuración de depuración usada por los IDE.

Ahora puede ejecutar la aplicación generada por la plantilla:

```console
dotnet run
```

Este comando restaurará en primer lugar las dependencias necesarias para compilar la aplicación y, después, creará la aplicación.

La configuración predeterminada escucha a `http://localhost:5000`. Abra un explorador y vaya a esa página. Verá un "¡Hola a todos!". .

Cuando haya terminado, puede cerrar la aplicación presionando <kbd>Ctrl</kbd>+<kbd>C</kbd>.

### <a name="anatomy-of-an-aspnet-core-application"></a>Anatomía de una aplicación de ASP.NET Core

Ahora que ha creado la aplicación, echemos un vistazo a cómo se implementa esta funcionalidad. Dos de los archivos generados son especialmente interesantes en este momento: WeatherMicroservice.csproj y Startup.cs. 

El archivo .csproj contiene información sobre el proyecto.
Los dos nodos que son más interesantes son `<TargetFramework>` y `<PackageReference>`.

El nodo `<TargetFramework>` especifica la versión de .NET que ejecutará esta aplicación.

Cada nodo `<PackageReference>` se usa para especificar un paquete necesario para esta aplicación.

La aplicación se implementa en Startup.cs. Este archivo contiene la clase de inicio.

La infraestructura de ASP.NET Core llama a los dos métodos para configurar y ejecutar la aplicación. El método `ConfigureServices` describe los servicios que son necesarios para esta aplicación. Va a crear un microservicio de Lean, así que no es necesario configurar ninguna dependencia. El método `Configure` configura los controladores para las solicitudes HTTP entrantes. La plantilla genera un controlador sencillo que responde a cualquier solicitud con el texto "¡Hola a todos!".

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

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

Todos los cambios que debe realzar se encuentran en la expresión lambda definida como el argumento para `app.Run` en la clase de inicio.

El argumento en la expresión lambda es el elemento `HttpContext` para la solicitud. Una de sus propiedades es el objeto `Request`. El objeto `Request` tiene una propiedad `Query` que contiene un diccionario de todos los valores en la cadena de consulta de la solicitud. La primera adición consiste en encontrar los valores de latitud y longitud:

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

Los valores del diccionario de `Query` son de tipo `StringValue`. Ese tipo puede contener una colección de cadenas. Para el servicio de información meteorológica, cada valor es una única cadena. Es por eso que existe la llamada a `FirstOrDefault()` en el código anterior. 

A continuación, debe convertir las cadenas en valores dobles. El método que va a usar para convertir la cadena en un doble es `double.TryParse()`:

```csharp
bool TryParse(string s, out double result);
```

Este método aprovecha parámetros de salida de C# para indicar si la cadena de entrada se puede convertir en un doble. Si la cadena representa un valor doble válido, el método devuelve true y el argumento `result` contiene el valor. Si la cadena no representa un valor doble válido, el método devuelve false.

Puede adaptar dicha API con el uso de un *método de extensión* que devuelve un *valor doble que acepta valores NULL*. Un *tipo de valor que acepta valores NULL* es un tipo que representa algún tipo de valor y también puede contener un valor que falta o un valor NULL. Un tipo que acepta valores NULL se representa mediante la anexión del carácter `?` a la declaración de tipos. 

Los métodos de extensión son métodos que se definen como métodos estáticos, pero al agregar el modificador `this` en el primer parámetro, se pueden llamar como si fueran miembros de esa clase. Los métodos de extensión solo se pueden definir en clases estáticas. Esta es la definición de la clase que contiene el método de extensión para el análisis:

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

Antes de llamar al método de extensión, cambie la referencia cultural actual a invariable:

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

Esto garantiza que la aplicación analiza los números de la misma forma en cualquier servidor, independientemente de su referencia cultural predeterminada.

Ahora puede usar el método de extensión para convertir los argumentos de cadena de consulta en el tipo doble:

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

Para probar fácilmente el código de análisis, actualice la respuesta para incluir los valores de los argumentos:

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

En este punto, puede ejecutar la aplicación web y ver si su código de análisis está funcionando. Agregue valores a la solicitud web en un explorador y verá los resultados actualizados.

### <a name="build-a-random-weather-forecast"></a>Creación de un pronóstico meteorológico aleatorio

La siguiente tarea consiste en crear un pronóstico meteorológico aleatorio. Comencemos con un contenedor de datos que contiene los valores que desea para un pronóstico meteorológico:

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

A continuación, cree un constructor que establezca esos valores de forma aleatoria. Este constructor usa los valores de la latitud y la longitud para inicializar el generador de números `Random`. Esto significa que el pronóstico para la misma ubicación es el mismo. Si cambia los argumentos para la latitud y la longitud, obtendrá un pronóstico diferente (ya que comienza con un valor de inicialización diferente).

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

Ahora puede generar el pronóstico de cinco días en el método de respuesta:

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a>Compilar la respuesta JSON

La tarea final de código en el servidor es convertir la lista `WeatherReport` en un documento JSON y devolverla al cliente. Comencemos creando el documento JSON. Agregará el serializador Newtonsoft de JSON a la lista de dependencias. Puede hacerlo mediante el comando `dotnet` siguiente:

```console
dotnet add package Newtonsoft.Json
```

A continuación, puede usar la clase `JsonConvert` para escribir el objeto en una cadena:

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

El código anterior convierte el objeto de pronóstico (una lista de objetos `WeatherForecast`) en un documento JSON. Después de haber construido el documento de respuesta, establezca el tipo de contenido en `application/json` y escriba la cadena.

Ahora, la aplicación se ejecuta y devuelve los pronósticos aleatorios.

## <a name="build-a-docker-image"></a>Creación de una imagen de Docker

La tarea final es ejecutar la aplicación en Docker. Vamos a crear un contenedor de Docker que ejecute una imagen de Docker que representa la aplicación.

Una ***imagen de Docker*** es un archivo que define el entorno de ejecución de la aplicación.

Un ***contenedor de Docker*** representa una instancia en ejecución de una imagen de Docker.

Por analogía, puede considerar la *imagen de Docker* como una *clase*y el *contenedor de Docker* como un objeto o una instancia de esa clase.  

El Dockerfile siguiente servirá para nuestros propósitos:

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

Repasemos su contenido.

La primera línea especifica la imagen de origen que se usa para generar la aplicación:

```
FROM microsoft/dotnet:2.1-sdk AS build
```

Docker le permite configurar una imagen de máquina basada en una plantilla de origen. Esto significa que no tiene que suministrar todos los parámetros de máquina cuando se inicia, solo tiene que proporcionar los cambios. Aquí los cambios van a ser incluir nuestra aplicación.

En este ejemplo, usaremos la versión `2.1-sdk` de la imagen de `dotnet`. Esta es la manera más fácil de crear un entorno de trabajo de Docker. Esta imagen incluye el tiempo de ejecución de .NET Core y el SDK de .NET Core.
Esto hace que resulte más fácil empezar a trabajar y compilar, pero también crea una imagen mayor, por lo que usaremos esta imagen para crear la aplicación y otra imagen para ejecutarla.

Las siguientes líneas instalan y compilan la aplicación:

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

El archivo de proyecto se copia desde el directorio actual en la máquina virtual de Docker y se restauran todos los paquetes. El uso de la CLI de dotnet significa que la imagen de Docker debe incluir el SDK de .NET Core. Luego, se copia el resto de la aplicación y el comando `dotnet
publish` compila y empaqueta la aplicación.

Por último, se crea una segunda imagen de Docker que ejecuta la aplicación:

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

Esta imagen usa la versión `2.1-aspnetcore-runtime` de la imagen de `dotnet`, que contiene todos los elementos necesarios para ejecutar aplicaciones de ASP.NET Core, pero no incluye el SDK de .NET Core. Esto significa que esta imagen no se puede usar para crear aplicaciones de .NET Core, pero también hace que la imagen final sea menor.

Para solucionar este problema, copiamos la aplicación integrada desde la primera imagen en la segunda.

El comando `ENTRYPOINT` informa a Docker qué comando inicia el servicio.

## <a name="building-and-running-the-image-in-a-container"></a>Compilación y ejecución de la imagen en un contenedor

Vamos a compilar una imagen y ejecutar el servicio dentro de un contenedor de Docker. No desea copiar todos los archivos de su directorio local en la imagen. En su lugar, va a compilar la aplicación en el contenedor. Creará un archivo `.dockerignore` para especificar los directorios que no se copian en la imagen. No desea copiar ninguno de los recursos de compilación. Especifique los directorios de compilación y publicación en el archivo `.dockerignore`:

```
bin/*
obj/*
out/*
```

Compile la imagen mediante el comando `docker build`. Ejecute el siguiente comando desde el directorio que contiene el código.

```console
docker build -t weather-microservice .
```

Este comando compila la imagen de contenedor en función de toda la información del Dockerfile. El argumento `-t` proporciona una etiqueta, o nombre, para esta imagen de contenedor. En la línea de comandos anterior, la etiqueta usada para el contenedor de Docker es `weather-microservice`. Cuando termina este comando, tendrá un contenedor listo para ejecutar el nuevo servicio. 

Ejecute el siguiente comando para iniciar el contenedor y el servicio:

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

La opción `-d` implica ejecutar el contenedor desasociado del terminal actual. Esto significa que no verá la salida del comando en el terminal. La opción `-p` indica la asignación de puertos entre el servicio y el host. Aquí dice que cualquier solicitud entrante en el puerto 80 se debe reenviar al puerto 80 en el contenedor. El uso de 80 coincide con el puerto en el que está escuchando el servicio, que es el puerto predeterminado para las aplicaciones de producción. El argumento `--name` nombra el contenedor en ejecución. Es un nombre adecuado que puede usar para trabajar con ese contenedor.

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

Cuando ejecutó el servicio en una ventana de comandos, pudo ver información de diagnóstico impresa para cada solicitud. Cuando el contenedor se ejecuta en modo de desconexión, no puede ver esa información. El comando attach de Docker le permite conectarse a un contenedor en ejecución para ver la información de registro.  Ejecute este comando desde una ventana de comandos:

```console
docker attach --sig-proxy=false hello-docker
```

El argumento `--sig-proxy=false` significa que los comandos <kbd>Ctrl</kbd>+<kbd>C</kbd> no se envían al proceso del contenedor, sino que detienen el comando `docker attach`. El argumento final es el nombre asignado al contenedor en el comando `docker run`. 

> [!NOTE]
> También puede usar el Id. de contenedor asignado a Docker para hacer referencia a cualquier contenedor. Si no especifica un nombre para el contenedor en `docker run`, debe usar el id. de contenedor.

Abra un explorador y vaya a su servicio. Verá los mensajes de diagnóstico en las ventanas de comandos desde el contenedor en ejecución conectado.

Presione <kbd>Ctrl</kbd>+<kbd>C</kbd> para detener el proceso de conexión.

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

En este tutorial, ha compilado un microservicio de ASP.NET Core y ha agregado unas cuantas características sencillas.

Ha compilado una imagen de un contenedor de Docker para ese servicio y ha ejecutado ese contenedor en el equipo. Ha conectado una ventana de terminal al servicio y ha visto los mensajes de diagnóstico de su servicio.

Por el camino, ha visto varias características del lenguaje C# en acción.
