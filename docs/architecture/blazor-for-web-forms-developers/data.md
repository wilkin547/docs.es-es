---
title: Acceso y administración de datos
description: Obtenga información sobre cómo obtener acceso a los datos y controlarlos en formularios Web Forms de ASP.NET y Blazor .
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/26/2020
ms.openlocfilehash: 8bd326e6952708b2099c3a575d6811990335df17
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267599"
---
# <a name="work-with-data"></a>Trabajar con datos

El acceso a datos es la red troncal de una aplicación de formularios Web Forms ASP.NET. Si va a crear formularios para la web, ¿qué ocurre con los datos? Con los formularios Web Forms, había varias técnicas de acceso a datos que podría usar para interactuar con una base de datos:

- Orígenes de datos
- ADO.NET
- Entity Framework

Los orígenes de datos eran controles que podía colocar en una página de formularios Web Forms y configurarlos como otros controles. Visual Studio proporciona un conjunto descriptivo de cuadros de diálogo para configurar y enlazar los controles a las páginas de formularios Web Forms. Los desarrolladores que disfrutan de un enfoque de "código bajo" o "sin código" prefieren esta técnica cuando se lanzaron por primera vez los formularios Web Forms.

![Orígenes de datos](media/data/datasources.png)

ADO.NET es el enfoque de bajo nivel para interactuar con una base de datos. Las aplicaciones pueden crear una conexión a la base de datos con comandos, conjuntos de registros y conjuntos de datos para interactuar. Los resultados se pueden enlazar a los campos de la pantalla sin mucho código. El inconveniente de este enfoque era que cada conjunto de objetos ADO.NET ( `Connection` , `Command` y `Recordset` ) se enlazó a las bibliotecas proporcionadas por un proveedor de bases de datos. El uso de estos componentes hace que el código sea rígido y difícil de migrar a una base de datos diferente.

## <a name="entity-framework"></a>Entity Framework

Entity Framework (EF) es el marco de trabajo de asignación relacional de objetos de código abierto mantenido por .NET Foundation. En la primera versión de .NET Framework, EF permite generar código para las conexiones de base de datos, los esquemas de almacenamiento y las interacciones. Con esta abstracción, puede centrarse en las reglas de negocios de la aplicación y permitir que un administrador de bases de datos de confianza administre la base de datos. En .NET Core, puede usar una versión actualizada de EF denominada EF Core. EF Core ayuda a generar y mantener las interacciones entre el código y la base de datos con una serie de comandos que están disponibles para usted mediante la `dotnet ef` herramienta de línea de comandos. Echemos un vistazo a algunos ejemplos para trabajar con una base de datos.

### <a name="ef-code-first"></a>Code First EF

Una forma rápida de empezar a crear las interacciones de base de datos es comenzar con los objetos de clase con los que desea trabajar. EF proporciona una herramienta que le ayudará a generar el código de base de datos adecuado para las clases. Este enfoque se denomina desarrollo "Code First". Considere la siguiente `Product` clase para una aplicación de escaparate de ejemplo que deseamos almacenar en una base de datos relacional como Microsoft SQL Server.

```csharp
public class Product
{
    public int Id { get; set; }

    [Required]
    public string Name { get; set; }

    [MaxLength(4000)]
    public string Description { get; set; }

    [Range(0, 99999,99)]
    [DataType(DataType.Currency)]
    public decimal Price { get; set; }
}
```

El producto tiene una clave principal y tres campos adicionales que se crearían en nuestra base de datos:  

- EF identificará la `Id` propiedad como clave principal por Convención.
- `Name` se almacenará en una columna configurada para el almacenamiento de texto. El `[Required]` atributo que decora esta propiedad agregará una `not null` restricción para ayudar a exigir este comportamiento declarado de la propiedad.
- `Description` se almacenará en una columna configurada para el almacenamiento de texto y tendrá una longitud máxima configurada de 4000 caracteres como indica el `[MaxLength]` atributo. El esquema de la base de datos se configurará con una columna denominada `MaxLength` con el tipo de datos `varchar(4000)` .
- La `Price` propiedad se almacenará como moneda. El `[Range]` atributo generará las restricciones adecuadas para evitar el almacenamiento de datos fuera de los valores mínimo y máximo declarados.

Necesitamos agregar esta `Product` clase a una clase de contexto de base de datos que defina las operaciones de conexión y traducción con nuestra base de datos.

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

La `MyDbContext` clase proporciona una propiedad que define el acceso y la traducción de la `Product` clase.  La aplicación configura esta clase para la interacción con la base de datos mediante las siguientes entradas en el `Startup` método de la clase `ConfigureServices` :

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

El código anterior se conectará a una base de datos de SQL Server con la cadena de conexión especificada. Puede colocar la cadena de conexión en el *appsettings.jsen* el archivo, variables de entorno u otras ubicaciones de almacenamiento de configuración y reemplazar esta cadena incrustada de forma adecuada.

A continuación, puede generar la tabla de base de datos adecuada para esta clase mediante los siguientes comandos:

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

El primer comando define los cambios que se realizan en el esquema de la base de datos como una nueva migración de EF denominada `Create Product table` .  Una migración define cómo aplicar y quitar los nuevos cambios de base de datos.

Una vez aplicado, tiene una `Product` tabla simple en la base de datos y algunas clases nuevas agregadas al proyecto que ayudan a administrar el esquema de la base de datos.  Puede encontrar estas clases generadas, de forma predeterminada, en una nueva carpeta denominada *migraciones*.  Cuando realice cambios en la `Product` clase o agregue más clases relacionadas que le gustaría interactuar con la base de datos, deberá volver a ejecutar los comandos de la línea de comandos con un nuevo nombre de la migración.  Este comando generará otro conjunto de clases de migración para actualizar el esquema de la base de datos.

### <a name="ef-database-first"></a>Database First EF

En el caso de las bases de datos existentes, puede generar las clases para EF Core mediante el uso de las herramientas de línea de comandos de .NET. Para aplicar scaffolding a las clases, use una variación del siguiente comando:

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

El comando anterior se conecta a la base de datos utilizando la cadena de conexión especificada y el `Microsoft.EntityFrameworkCore.SqlServer` proveedor. Una vez conectado, se crea una clase de contexto de base de datos denominada `MyDbContext` . Además, las clases auxiliares se crean para `Product` las `Customer` tablas y que se especificaron con las `-t` Opciones. Hay muchas opciones de configuración para este comando con el fin de generar la jerarquía de clases adecuada para la base de datos. Para obtener una referencia completa, consulte [la documentación del comando](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).

Puede encontrar más información sobre [EF Core](/ef/core/) en el sitio de Microsoft docs.

## <a name="interact-with-web-services"></a>Interacción con servicios Web

Cuando ASP.NET se lanzó por primera vez, los servicios SOAP eran el mejor método para que los clientes y servidores web intercambien datos. Ha cambiado mucho desde ese momento y las interacciones preferidas con los servicios se han desplazado a interacciones directas del cliente HTTP. Con ASP.NET Core y Blazor , puede registrar la configuración de `HttpClient` en el `Startup` método de la clase `ConfigureServices` . Use esa configuración cuando necesite interactuar con el punto de conexión HTTP. Considere el siguiente código de configuración:

```csharp
services.AddHttpClient("github", client =>
{
    client.BaseAddress = new Uri("http://api.github.com/");
    // Github API versioning
    client.DefaultRequestHeaders.Add("Accept", "application/vnd.github.v3+json");
    // Github requires a user-agent
    client.DefaultRequestHeaders.Add("User-Agent", "BlazorWebForms-Sample");
});
```

Siempre que necesite tener acceso a los datos de GitHub, cree un cliente con el nombre `github` . El cliente está configurado con la dirección base y los encabezados de solicitud se establecen adecuadamente. Inserte el `IHttpClientFactory` en los Blazor componentes con la `@inject` Directiva o un `[Inject]` atributo en una propiedad. Cree el cliente con nombre e interactúe con los servicios mediante la siguiente sintaxis:

```razor
@inject IHttpClientFactory factory

...

@code {
    protected override async Task OnInitializedAsync()
    {
        var client = factory.CreateClient("github");
        var response = await client.GetAsync("repos/dotnet/docs/issues");
        response.EnsureStatusCode();
        var content = async response.Content.ReadAsStringAsync();
    }
}
```

Este método devuelve la cadena que describe la colección de problemas en el repositorio de github *dotnet/docs* . Devuelve contenido en formato JSON y se deserializa en los objetos de problema de GitHub correspondientes. Hay muchas maneras de configurar `HttpClientFactory` para proporcionar objetos preconfigurados `HttpClient` . Intente configurar varias `HttpClient` instancias con distintos nombres y puntos de conexión para los diversos servicios web con los que trabaja. Este enfoque hará que sus interacciones con esos servicios sean más fáciles de trabajar en cada página. Para obtener más información, lea [la documentación de IHttpClientFactory](/aspnet/core/fundamentals/http-requests).

>[!div class="step-by-step"]
>[Anterior](forms-validation.md)
>[Siguiente](middleware.md)
