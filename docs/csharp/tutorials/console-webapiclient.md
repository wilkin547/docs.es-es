---
title: Creación de un cliente de REST con .NET Core
description: Este tutorial le enseña varias características de .NET Core y el lenguaje C#.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 5796df2d2fd8c4d9aaca783d720448c90858c067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156862"
---
# <a name="rest-client"></a>Cliente REST

Este tutorial le enseña varias características de .NET Core y el lenguaje C#. Aprenderá lo siguiente:

* Los aspectos básicos de la CLI de .NET Core.
* Información general de las características del lenguaje C#.
* Administración de dependencias con NuGet
* Comunicaciones HTTP
* Procesamiento de información de JSON
* Administración de la configuración con atributos

Creará una aplicación que emite solicitudes HTTP a un servicio REST en GitHub. Leerá información en formato JSON y convertirá ese paquete JSON en objetos de C#. Por último, verá cómo trabajar con objetos de C#.

Este tutorial incluye muchas características. Vamos a compilarlas una a una.

Si prefiere seguir el [ejemplo final](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) de este tema, puede descargarlo. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página [Descargas de .NET Core](https://dotnet.microsoft.com/download). Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.
Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

## <a name="create-the-application"></a>Crear la aplicación

El primer paso es crear una nueva aplicación. Abra un símbolo del sistema y cree un nuevo directorio para la aplicación. Conviértalo en el directorio actual. Escriba el siguiente comando en la ventana de consola:

```dotnetcli
dotnet new console --name WebApiClient
```

Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo". El nombre del proyecto es "WebApiClient". Como se trata de un proyecto nuevo, ninguna de las dependencias está en su lugar, así que la primera ejecución descargará .NET Core Framework, instalará un certificado de desarrollo y ejecutará el gestor de paquetes NuGet para restaurar las dependencias que faltan.

Antes de empezar a hacer modificaciones, escriba `dotnet run` ([vea la nota](#dotnet-restore-note)) en el símbolo del sistema para ejecutar la aplicación. `dotnet run` ejecuta automáticamente `dotnet restore` si el entorno no tiene dependencias. También ejecuta `dotnet build` si hay que volver a compilar la aplicación.
Después de la instalación inicial, solo tendrá que ejecutar `dotnet restore` o `dotnet build` cuando tenga sentido para su proyecto.

## <a name="adding-new-dependencies"></a>Adición de nuevas dependencias

Uno de los principales objetivos de diseño de .NET Core es minimizar el tamaño de la instalación de .NET. Si una aplicación necesita bibliotecas adicionales para algunas de sus características, agregará esas dependencias al archivo de proyecto (\*.csproj) de C#. En nuestro ejemplo, deberá agregar el paquete `System.Runtime.Serialization.Json` para que su aplicación pueda procesar respuestas JSON.

Necesitará el paquete `System.Runtime.Serialization.Json` para esta aplicación. Agréguelo al proyecto ejecutando el siguiente comando de la [CLI de .NET](../../core/tools/dotnet-add-package.md):

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a>Realización de las solicitudes web

Ahora está listo para comenzar a recuperar datos de la Web. En esta aplicación, leerá información de la [API de GitHub](https://developer.github.com/v3/). Vamos a leer información sobre los proyectos que aparecen en el paraguas [.NET Foundation](https://www.dotnetfoundation.org/). Para comenzar, realizará la solicitud a la API de GitHub para recuperar información sobre los proyectos. El punto de conexión que usará es: <https://api.github.com/orgs/dotnet/repos>. Quiere recuperar toda la información sobre estos proyectos, así que usará una solicitud HTTP GET.
El explorador también usa solicitudes HTTP GET, por lo que puede pegar esa dirección URL en él para ver la información que recibirá y procesará.

Usará la clase <xref:System.Net.Http.HttpClient> para realizar solicitudes web. Al igual que las API de .NET modernas, <xref:System.Net.Http.HttpClient> admite solo métodos asincrónicos para sus API de ejecución prolongada.
Para empezar, cree un método asincrónico. Rellenará la implementación mientras compila la funcionalidad de la aplicación. Para comenzar, abra el archivo `program.cs` en el directorio del proyecto y agregue el siguiente método a la clase `Program`:

```csharp
private static async Task ProcessRepositories()
{
}
```

Tiene que agregar una directiva `using` en la parte superior del método `Main` para que el compilador de C# reconozca el tipo <xref:System.Threading.Tasks.Task>:

```csharp
using System.Threading.Tasks;
```

Si compila el proyecto en este momento, obtendrá una advertencia generada para este método, porque no contiene ningún operador `await` y se ejecutará de forma sincrónica. Por ahora omítala; agregará los operadores `await` a medida que rellena el método.

A continuación, cambie el nombre del espacio de nombres definido en la instrucción `namespace` de su valor predeterminado de `ConsoleApp` a `WebAPIClient`. Más adelante definiremos una clase `repo` en este espacio de nombres.

A continuación, actualice el método `Main` para llamar a este método. El método `ProcessRepositories` devuelve una tarea. No debe salir del programa antes de que esta finalice. Por lo tanto, debe cambiar la firma de `Main`. Agregue el modificador `async` y cambie el tipo de valor devuelto a `Task`. A continuación, en el cuerpo del método, agregue una llamada a `ProcessRepositories`. Agregue la palabra clave `await` a esa llamada al método:

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

Ahora, tiene un programa que no hace nada, pero lo hace de forma asincrónica. Vamos a mejorarlo.

Primero necesita un objeto capaz de recuperar datos de la Web; para ello, puede usar <xref:System.Net.Http.HttpClient>. Este objeto administra la solicitud y las respuestas. Cree una sola instancia de ese tipo en la clase `Program`, dentro del archivo *Program.cs*.

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

Volvamos al método `ProcessRepositories` y rellene una primera versión de él:

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

También tiene que agregar dos nuevas directivas `using` en la parte superior del archivo para que este se compile:

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

Esta primera versión realiza una solicitud web para leer la lista de todos los repositorios en la organización dotnet foundation. (El id. de gitHub para .NET Foundation es "dotnet"). Las primeras líneas configuran el objeto <xref:System.Net.Http.HttpClient> para esta solicitud. En primer lugar, se configura para aceptar las respuestas JSON de GitHub.
Este formato es simplemente JSON. La siguiente línea agrega un encabezado de agente de usuario a todas las solicitudes desde este objeto. Estos dos encabezados se comprueban mediante el código de servidor de GitHub y son necesarios para recuperar información de GitHub.

Después de haber configurado el objeto <xref:System.Net.Http.HttpClient>, realizará una solicitud web y recuperará la respuesta. En esta primera versión, usa el método de conveniencia <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>. Este método de conveniencia inicia una tarea que realiza la solicitud web y, a continuación, cuando la solicitud se devuelve, lee la secuencia de respuesta y extrae el contenido de la secuencia. El cuerpo de la respuesta se devuelve como <xref:System.String>. La cadena está disponible cuando finaliza la tarea.

Las dos últimas líneas de este método esperan a la tarea y, luego, imprimen la respuesta en la consola.
Compile la aplicación y ejecútela. La advertencia de compilación desaparece ahora, porque `ProcessRepositories` contiene ahora un operador `await`. Verá una pantalla larga de texto con formato de JSON.

## <a name="processing-the-json-result"></a>Procesamiento del resultado JSON

Llegados a este punto, ha escrito el código para recuperar una respuesta de un servidor web y mostrar el texto contiene esa respuesta. A continuación, vamos a convertir esa respuesta JSON en objetos de C#.

La clase <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> serializa objetos a JSON y deserializa JSON en objetos. Empiece por definir una clase para representar el objeto JSON `repo` devuelto desde la API de GitHub:

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

Coloque el código anterior en un archivo nuevo llamado "repo.cs". Esta versión de la clase representa la ruta de acceso más sencilla de procesar datos JSON. El nombre de clase y el nombre de miembro coinciden con los nombres usados en el paquete JSON, en lugar de las siguientes convenciones de C#. Más adelante proporcionará algunos atributos de configuración para corregir esto. Esta clase muestra otra característica importante de la serialización y deserialización de JSON: No todos los campos del paquete JSON forman parte de esta clase.
El serializador JSON pasará por alto la información que no esté incluida en el tipo de clase que se va a usar.
Esta característica facilita la creación de tipos que funcionan con solo un subconjunto de los campos del paquete JSON.

Ahora que ha creado el tipo, vamos a deserializarlo.

A continuación, usará el serializador para convertir JSON en objetos de C#. Reemplace la llamada a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> en su método `ProcessRepositories` por las tres líneas siguientes:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

Está usando un nuevo espacio de nombres, por lo que deberá agregarlo también en la parte superior del archivo:

```csharp
using System.Text.Json;
```

Tenga en cuenta que ahora usa <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> en lugar de <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>. El serializador usa una secuencia en lugar de una cadena como su origen. Vamos a explicar algunas características del lenguaje C# que se usan en la segunda línea del fragmento de código anterior. El primer argumento para <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> es una expresión `await`. Los otros dos parámetros son opcionales y se omiten en el fragmento de código. Las expresiones Await pueden aparecer prácticamente en cualquier parte del código, aunque hasta ahora, únicamente las ha visto como parte de una instrucción de asignación. El método `Deserialize` es *genérico*, lo que significa que debe proporcionar argumentos de tipo para el tipo de objetos que se debe crear a partir del texto JSON. En este ejemplo, se va a deserializar a un `List<Repository>`, que es otro objeto genérico, <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. La clase `List<>` administra una colección de objetos. El argumento de tipo declara el tipo de objetos almacenados en `List<>`. El texto JSON representa una colección de objetos de repositorio, por lo que el argumento de tipo es `Repository`.

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

Antes de agregar más características, vamos a abordar la propiedad `name` mediante el atributo `[JsonPropertyName]`. Realice los siguientes cambios en la declaración del campo `name` en repo.cs:

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

Para usar el atributo `[JsonPropertyName]`, tiene que agregar el espacio de nombres <xref:System.Text.Json.Serialization> a las directivas `using`:

```csharp
using System.Text.Json.Serialization;
```

Este cambio significa que debe cambiar el código que escribe el nombre de cada repositorio en program.cs:

```csharp
Console.WriteLine(repo.Name);
```

Ejecute `dotnet run` para asegurarse de que tiene las asignaciones correctas. Debería ver la misma salida que antes.

Vamos a hacer un cambio más antes de agregar nuevas características. El método `ProcessRepositories` puede realizar el trabajo asincrónico y devolver una colección de los repositorios. Vamos a volver a `List<Repository>` desde ese método y a mover el código que escribe la información en el método `Main`.

Cambie la signatura de `ProcessRepositories` para devolver una tarea cuyo resultado sea una lista de objetos `Repository`:

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

A continuación, devuelva solo los repositorios después de procesar la respuesta JSON:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

El compilador genera el objeto `Task<T>` para la devolución porque ha marcado este método como `async`.
A continuación, vamos a modificar el método `Main` para que capture esos resultados y escriba cada nombre de repositorio en la consola. Su método `Main` tiene ahora este aspecto:

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a>Leer más información

Para terminar esto, vamos a procesar unas cuantas propiedades más del paquete JSON que se envía desde la API de GitHub. No quiere captar toso, sino que con solo agregar unas cuantas propiedades se demostrarán más características del lenguaje C#.

Comencemos por agregar algunos tipos simples más a la definición de clase `Repository`. Agregue estas propiedades a esa clase:

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

Estas propiedades tienen integradas conversiones de tipo cadena (que es lo que contienen los paquetes JSON) para el tipo de destino. Puede que no esté familiarizado con el tipo <xref:System.Uri>. Representa un identificador URI, o en este caso, una dirección URL. En el caso de los tipos `Uri` y `int`, si el paquete JSON contiene datos que no se convierten al tipo de destino, la acción de serialización iniciará una excepción.

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

Ese formato no sigue ninguno de los formatos estándar <xref:System.DateTime> de .NET. Por este motivo, deberá escribir un método de conversión personalizado. Probablemente tampoco querrá la cadena sin formato expuesta a los usuarios de la clase `Repository`. Los atributos pueden también ayudarle a controlar eso. En primer lugar, defina una propiedad `public` que contendrá la representación de cadena de la fecha y hora en la clase `Repository` y una propiedad `LastPush` `readonly` que devuelve una cadena con formato que representa la fecha devuelta:

```csharp
[JsonPropertyName("pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

Vamos a repasar las nuevas construcciones que acabamos de definir. La propiedad `LastPush` se define utilizando un *miembro con forma de expresión* para el descriptor de acceso `get`. No hay descriptor de acceso `set`. Omitiendo el descriptor de acceso `set` es la forma en que se define una propiedad *de solo lectura* en C#. (Sí, puede crear propiedades de *solo escritura* en C#, pero su valor es limitado). El método <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analiza una cadena y crea un objeto <xref:System.DateTime> con un formato de fecha proporcionado, y agrega metadatos adicionales a `DateTime` mediante un objeto `CultureInfo`. Si se produce un error en la operación de análisis, el descriptor de acceso de propiedad inicia una excepción.

Para usar <xref:System.Globalization.CultureInfo.InvariantCulture>, tiene que agregar el espacio de nombres <xref:System.Globalization> a las directivas `using` de `repo.cs`:

```csharp
using System.Globalization;
```

Finalmente, agregue una instrucción más de salida en la consola y ya estará listo para compilar y ejecutar de nuevo esta aplicación:

```csharp
Console.WriteLine(repo.LastPush);
```

La versión debe coincidir ahora con el [ejemplo terminado](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).

## <a name="conclusion"></a>Conclusión

En este tutorial se ha mostrado cómo realizar solicitudes web, analizar el resultado y visualizar las propiedades de los resultados. También ha agregado nuevos paquetes como dependencias en el proyecto. Ha visto algunas de las características del lenguaje C# compatibles con técnicas orientadas a objetos.

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
