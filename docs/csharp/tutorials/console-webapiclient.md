---
title: "Creación de un cliente de REST con .NET Core"
description: "Este tutorial le enseña varias características de .NET Core y el lenguaje C#."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.translationtype: HT
ms.sourcegitcommit: b647c5dc4e565f9813212d75fab4a2e46c1a47b9
ms.openlocfilehash: 8c747f65dca44fcca25fe67dccaa897561eefcc7
ms.contentlocale: es-es
ms.lasthandoff: 09/12/2017

---

# <a name="rest-client"></a>Cliente REST

## <a name="introduction"></a>Introducción
Este tutorial le enseña varias características de .NET Core y el lenguaje C#. Aprenderá lo siguiente:
*   Los aspectos básicos de la interfaz de línea de comandos (CLI) de .NET Core
*   Información general de las características del lenguaje C#.
*   Administración de dependencias con NuGet
*   Comunicaciones HTTP
*   Procesamiento de información de JSON
*   Administración de la configuración con atributos 

Creará una aplicación que emite solicitudes HTTP a un servicio REST en GitHub. Leerá información en formato JSON y convertirá ese paquete JSON en objetos de C#. Por último, verá cómo trabajar con objetos de C#.

Hay muchas características en este tutorial. Vamos a compilarlas una a una.

Si prefiere seguir el [ejemplo final](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) de este tema, puede descargarlo. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Requisitos previos
Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core). Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker. Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.
## <a name="create-the-application"></a>Crear la aplicación
El primer paso es crear una nueva aplicación. Abra un símbolo del sistema y cree un nuevo directorio para la aplicación. Conviértalo en el directorio actual. Escriba el comando `dotnet new console` en el símbolo del sistema. Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".

Antes de comenzar a realizar modificaciones, vamos a recorrer los pasos para ejecutar la aplicación Hola a todos sencilla. Después de crear la aplicación, escriba `dotnet restore` en el símbolo del sistema. Este comando ejecuta el proceso de restauración de paquetes de NuGet. NuGet es un administrador de paquetes .NET. Este comando permite descargar cualquiera de las dependencias que faltan para el proyecto. Como se trata de un nuevo proyecto, ninguna de las dependencias está en su lugar, así que con la primera ejecución se descargará .NET Core Framework. Después de este paso inicial, solo deberá ejecutar `dotnet restore` al agregar nuevos paquetes dependientes, o actualizar las versiones de cualquiera de sus dependencias.  

Después de restaurar los paquetes, ejecutará `dotnet build`. Esta acción ejecuta el motor de compilación y crea la aplicación. Por último, ejecute `dotnet run` para ejecutar la aplicación.

## <a name="adding-new-dependencies"></a>Adición de nuevas dependencias
Uno de los objetivos de diseño principales para .NET Core es reducir el tamaño de la instalación de .NET Framework. El marco de trabajo de la aplicación .NET Core solo contiene los elementos más comunes del marco completo .NET. Si una aplicación necesita bibliotecas adicionales para algunas de sus características, agregará esas dependencias al archivo de proyecto (*.csproj) de C#. En nuestro ejemplo, deberá agregar el paquete `System.Runtime.Serialization.Json` para que su aplicación pueda procesar respuestas JSON.

Abra el archivo de proyecto `csproj`. La primera línea del archivo debe aparecer como:

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

Agregue lo siguiente inmediatamente después de esta línea: 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
La mayoría de los editores de código proporcionarán la finalización de las distintas versiones de estas bibliotecas. Normalmente, querrá usar la versión más reciente de cualquier paquete que agregue. Sin embargo, es importante asegurarse de que las versiones de todos los paquetes coincidan y que también coincida la versión del marco de trabajo de la aplicación de .NET Core.

Una vez realizados estos cambios, debe ejecutar de nuevo `dotnet restore` para que el paquete se instale en su sistema.

## <a name="making-web-requests"></a>Realización de las solicitudes web
Ahora está listo para comenzar a recuperar datos de la Web. En esta aplicación, leerá información de la [API de GitHub](https://developer.github.com/v3/). Vamos a leer información sobre los proyectos que aparecen en el paraguas [.NET Foundation](http://www.dotnetfoundation.org/). Para comenzar, realizará la solicitud a la API de GitHub para recuperar información sobre los proyectos. El punto de conexión que se usará es: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos). Quiere recuperar toda la información sobre estos proyectos, así que usará una solicitud HTTP GET.
El explorador también usa solicitudes HTTP GET, por lo que puede pegar esa dirección URL en él para ver la información que recibirá y procesará.

Usará la clase @System.Net.Http.HttpClient para realizar solicitudes web. Al igual que las API de .NET modernas, @System.Net.Http.HttpClient admite solo métodos asincrónicos para sus API de ejecución prolongada.
Para empezar, cree un método asincrónico. Rellenará la implementación mientras compila la funcionalidad de la aplicación. Para comenzar, abra el archivo `program.cs` en el directorio del proyecto y agregue el siguiente método a la clase `Program`:

```csharp
private static async Task ProcessRepositories()
{
    
}
```

Deberá agregar una instrucción `using` en la parte superior del método `Main` para que el compilador de C# reconozca el tipo @System.Threading.Tasks.Task:

```csharp
using System.Threading.Tasks;
```

Si compila el proyecto en este momento, obtendrá una advertencia generada para este método, porque no contiene ningún operador `await` y se ejecutará de forma sincrónica. Por ahora omítala; agregará los operadores `await` a medida que rellena el método.

A continuación, cambie el nombre del espacio de nombres definido en la instrucción `namespace` de su valor predeterminado de `ConsoleApp` a `WebAPIClient`. Más adelante definiremos una clase `repo` en este espacio de nombres.

A continuación, actualice el método `Main` para llamar a este método. El método `ProcessRepositories` devuelve una tarea. No debe salir del programa antes de que finalice la tarea. Por lo tanto, debe usar el método `Wait` para bloquear y esperar a que finalice la tarea:

```csharp
public static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

Ahora, tiene un programa que no hace nada, pero lo hace de forma asincrónica. Volvamos al método `ProcessRepositories` y rellene una primera versión de él:

```csharp
private static async Task ProcessRepositories()
{
    var client = new HttpClient();
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

También deberá agregar dos nuevas instrucciones using en la parte superior del archivo para compilar esto:

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

Esta primera versión realiza una solicitud web para leer la lista de todos los repositorios en la organización dotnet foundation. (El id. de gitHub para .NET Foundation es "dotnet"). En primer lugar, cree un nuevo @System.Net.Http.HttpClient. Este objeto administra la solicitud y las respuestas. Las siguientes líneas configuran el objeto @System.Net.Http.HttpClient para esta solicitud. En primer lugar, se configura para aceptar las respuestas JSON de GitHub.
Este formato es simplemente JSON. La siguiente línea agrega un encabezado de agente de usuario a todas las solicitudes desde este objeto. Estos dos encabezados se comprueban mediante el código de servidor de GitHub y son necesarios para recuperar información de GitHub.

Después de haber configurado el objeto @System.Net.Http.HttpClient, realizará una solicitud web y recuperará la respuesta. En esta primera versión, usa el método de conveniencia <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=fullname>. Este método de conveniencia inicia una tarea que realiza la solicitud web y, a continuación, cuando la solicitud se devuelve, lee la secuencia de respuesta y extrae el contenido de la secuencia. El cuerpo de la respuesta se devuelve como @System.String. La cadena está disponible cuando finaliza la tarea. 

Las dos últimas líneas de este método esperan a la tarea y, luego, imprimen la respuesta en la consola.
Compile la aplicación y ejecútela. La advertencia de compilación desaparece ahora, porque `ProcessRepositories` contiene ahora un operador `await`. Verá una pantalla larga de texto con formato de JSON.   

## <a name="processing-the-json-result"></a>Procesamiento del resultado JSON

Llegados a este punto, ha escrito el código para recuperar una respuesta de un servidor web y mostrar el texto contiene esa respuesta. A continuación, vamos a convertir esa respuesta JSON en objetos de C#.

El serializador JSON convierte datos JSON en objetos de C#. La primera tarea consiste en definir un tipo de clase de C# para que contenga la información que se usa de esta respuesta. Vamos a crear esto lentamente, así que comience con un tipo simple de C# que contiene el nombre del repositorio:

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

Coloque el código anterior en un archivo nuevo llamado "repo.cs". Esta versión de la clase representa la ruta de acceso más sencilla de procesar datos JSON. El nombre de clase y el nombre de miembro coinciden con los nombres usados en el paquete JSON, en lugar de las siguientes convenciones de C#. Más adelante proporcionará algunos atributos de configuración para corregir esto. Esta clase demuestra otra característica importante de la serialización y deserialización JSON: no todos los campos del paquete JSON forman parte de esta clase.
El serializador JSON pasará por alto la información que no esté incluida en el tipo de clase que se va a usar.
Esta característica facilita la creación de tipos que funcionan con solo un subconjunto de los campos del paquete JSON.

Ahora que ha creado el tipo, vamos a deserializarlo. Deberá crear un objeto @System.Runtime.Serialization.Json.DataContractJsonSerializer. Este objeto debe conocer el tipo CLR esperado para que el paquete JSON se recupere. El paquete de GitHub contiene una secuencia de repositorios, por lo que un tipo `List<repo>` es el tipo correcto. Agregue la línea siguiente al método `ProcessRepositories`:

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

Va a usar dos nuevos espacios de nombres, por lo que también deberá agregarlos:

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

A continuación, usará el serializador para convertir JSON en objetos de C#. Reemplace la llamada a @System.Net.Http.HttpClient.GetStringAsync(System.String) en su método `ProcessRepositories` por las dos líneas siguientes:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

Observe que ahora usa @System.Net.Http.HttpClient.GetStreamAsync(System.String) en lugar de @System.Net.Http.HttpClient.GetStringAsync(System.String). El serializador usa una secuencia en lugar de una cadena como su origen. Vamos a explicar algunas características del lenguaje C# que se usan en la segunda línea anterior. El argumento para @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) es una expresión `await`. Las expresiones Await pueden aparecer prácticamente en cualquier parte del código, aunque hasta ahora, únicamente las ha visto como parte de una instrucción de asignación.

En segundo lugar, el operador `as` convierte el tipo de tiempo de compilación `object` a `List<repo>`. La declaración de @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) declara que devuelve un objeto de tipo <xref:System.Object?displayProperty=fullName>. @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) devolverá el tipo especificado al construirlo (`List<repo>` en este tutorial). Si la conversión no se realiza correctamente, el operador `as` se evalúa como `null`, en lugar de iniciar una excepción.

Casi ha terminado con esta sección. Ahora que ha convertido el código JSON a objetos de C#, vamos a mostrar el nombre de cada repositorio. Reemplace las líneas donde pone:

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

por lo siguiente:

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

Compile y ejecute la aplicación. Se imprimirán los nombres de los repositorios que forman parte de .NET Foundation.

## <a name="controlling-serialization"></a>Control de la serialización

Antes de agregar más características, vamos a abordar el tipo `repo` y hacer que siga convenciones de C# más estándar. Para ello, anotará el tipo `repo` con *atributos* que controlan cómo funciona el serializador de JSON. En su caso, usará estos atributos para definir una asignación entre los nombres de claves JSON y los nombres de miembros y clases de C#. Los dos atributos usados son el atributo `DataContract` y el atributo `DataMember`. Por convención, todas las clases de atributo acaban en el sufijo `Attribute`. Sin embargo, no es necesario usar ese sufijo cuando aplique un atributo. 

Los atributos `DataContract` y `DataMember` están en una biblioteca diferente, por lo que deberá agregar esa biblioteca a su archivo de proyecto de C# como una dependencia. Agregue la siguiente línea a la sección `<ItemGroup>` del archivo de proyecto:

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

Después de guardar el archivo, ejecute `dotnet restore` para recuperar este paquete.

A continuación, abra el archivo `repo.cs`. Vamos a cambiar el nombre por Pascal Case y a deletrear totalmente el nombre `Repository`. Queremos asignar nodos "repo" de JSON a este tipo, así que deberá instalar el atributo `DataContract` en la declaración de clase. Establecerá la propiedad `Name` del atributo en el nombre de los nodos JSON que se asignan a este tipo:

```csharp
[DataContract(Name="repo")]
public class Repository
```

@System.Runtime.Serialization.DataContractAttribute es miembro del espacio de nombres @System.Runtime.Serialization, así que deberá agregar la instrucción `using` adecuada al principio del archivo:

```csharp
using System.Runtime.Serialization;
```

Ha cambiado el nombre de la clase `repo` por `Repository`, así que deberá hacer el mismo cambio en Program.cs (algunos editores pueden admitir una refactorización de cambio de nombre que realizará este cambio automáticamente):

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

A continuación, vamos a realizar el mismo cambio con el campo `name` mediante la clase @System.Runtime.Serialization.DataMemberAttribute. Realice los siguientes cambios en la declaración del campo `name` en repo.cs:

```csharp
[DataMember(Name="name")]
public string Name;
```

Este cambio significa que debe cambiar el código que escribe el nombre de cada repositorio en program.cs:

```csharp
Console.WriteLine(repo.Name);
```

Realice una acción `dotnet build` seguida de una acción `dotnet run` para asegurarse de que tiene las asignaciones correctas. Debería ver la misma salida que antes. Antes de procesar más propiedades desde el servidor web, vamos a hacer un cambio más a la clase `Repository`. El miembro `Name` es un campo de acceso público. No es una buena práctica orientada a objetos, así que vamos a cambiarlo por una propiedad. Para nuestros propósitos, no necesitamos ejecutar ningún código específico al obtener o establecer la propiedad, pero al cambiar a una propiedad es más sencillo agregar esos cambios más adelante sin interrumpir el código que usa la clase `Repository`.

Quite la definición de campo y reemplácela por una [propiedad implementada automáticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md):

```csharp
public string Name { get; set; }
```

El compilador genera el cuerpo de los descriptores de acceso `get` y `set`, así como un campo privado para almacenar el nombre. Sería similar al siguiente código que podría escribir a mano:

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

Vamos a hacer un cambio más antes de agregar nuevas características. El método `ProcessRepositories` puede realizar el trabajo asincrónico y devolver una colección de los repositorios. Vamos a volver a `List<Repository>` desde ese método y a mover el código que escribe la información en el método `Main`.

Cambie la signatura de `ProcessRepositories` para devolver una tarea cuyo resultado sea una lista de objetos `Repository`:

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

A continuación, devuelva solo los repositorios después de procesar la respuesta JSON:

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

El compilador genera el objeto `Task<T>` para la devolución porque ha marcado este método como `async`.
A continuación, vamos a modificar el método `Main` para que capture esos resultados y escriba cada nombre de repositorio en la consola. Su método `Main` tiene ahora este aspecto:

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

El acceso a la propiedad `Result` de una tarea se bloquea hasta que finaliza la tarea. Normalmente, preferiría esperar (`await`) a que finalizara la tarea, como en el método `ProcessRepositories`, pero eso no se permite en el método `Main`.

## <a name="reading-more-information"></a>Leer más información

Para terminar esto, vamos a procesar unas cuantas propiedades más del paquete JSON que se envía desde la API de GitHub. No quiere captar toso, sino que con solo agregar unas cuantas propiedades se demostrarán más características del lenguaje C#.

Comencemos por agregar algunos tipos simples más a la definición de clase `Repository`. Agregue estas propiedades a esa clase:

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

Estas propiedades tienen integradas conversiones de tipo cadena (que es lo que contienen los paquetes JSON) para el tipo de destino. Puede que no esté familiarizado con el tipo @System.Uri. Representa un identificador URI, o en este caso, una dirección URL. En el caso de los tipos `Uri` y `int`, si el paquete JSON contiene datos que no se convierten al tipo de destino, la acción de serialización iniciará una excepción.

Una vez agregados estos, actualice el método `Main` para mostrar estos elementos:

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```
Como paso final, vamos a agregar la información de la última operación de inserción. El formato de esta información es este en la respuesta JSON:

```json
2016-02-08T21:27:00Z
```

Ese formato no sigue ninguno de los formatos estándar @System.DateTime de .NET. Por este motivo, deberá escribir un método de conversión personalizado. Probablemente tampoco querrá la cadena sin formato expuesta a los usuarios de la clase `Repository`. Los atributos pueden también ayudarle a controlar eso. En primer lugar, defina una propiedad `private` que contenga la representación de cadena de la fecha y hora de su clase `Repository`:

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

El atributo `DataMember` informa al serializador que esta se debe procesar, aunque no sea un miembro público. A continuación, debe escribir una propiedad pública de solo lectura que convierta la cadena en un objeto @System.DateTime válido y que devuelva ese objeto @System.DateTime:

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

Repasemos las nuevas construcciones anteriores. El atributo `IgnoreDataMember` indica al serializador que este tipo no se debe leer ni escribir de cualquier objeto JSON. Esta propiedad contiene solo contiene un descriptor de acceso `get`. No hay descriptor de acceso `set`. Así es cómo se define la propiedad de *solo lectura* en C#. (Sí, puede crear propiedades de *solo escritura* en C#, pero su valor es limitado). El método @System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider) analiza una cadena y crea un objeto @System.DateTime mediante un formato de fecha proporcionado, y agrega metadatos adicionales a `DateTime` mediante un objeto `CultureInfo`. Si se produce un error en la operación de análisis, el descriptor de acceso de propiedad inicia una excepción.

Para usar @System.Globalization.CultureInfo.InvariantCulture, deberá agregar el espacio de nombres @System.Globalization a las instrucciones `using` en `repo.cs`:

```csharp
using System.Globalization;
```

Finalmente, agregue una instrucción más de salida en la consola y ya estará listo para compilar y ejecutar de nuevo esta aplicación:

```csharp
Console.WriteLine(repo.LastPush);
```

La versión debe coincidir ahora con el [ejemplo terminado](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).
 
## <a name="conclusion"></a>Conclusión

En este tutorial se ha mostrado cómo realizar solicitudes web, analizar el resultado y visualizar las propiedades de los resultados. También ha agregado nuevos paquetes como dependencias en el proyecto. Ha visto algunas de las características del lenguaje C# compatibles con técnicas orientadas a objetos.


