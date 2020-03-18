---
title: 'Azure Functions: Aplicaciones sin servidor'
description: Azure Functions proporciona funcionalidades sin servidor mediante varios lenguajes (C#, JavaScript, Java) y plataformas para proporcionar código de escalado instantáneo orientado a eventos.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401488"
---
# <a name="azure-functions"></a>Comprobación de

Azure Functions proporciona una experiencia de proceso sin servidor. Un *desencadenador* invoca una función (por ejemplo, el acceso a un punto de conexión HTTP o un temporizador) y ejecuta un bloque de código o lógica de negocios. Las funciones también admiten *enlaces* especializados que se conectan a recursos como los de almacenamiento y colas.

![Logotipo de Azure Functions](./media/azure-functions-logo.png)

Hay dos versiones de la plataforma de Azure Functions. La versión heredada admite la versión completa de .NET Framework y el nuevo entorno de ejecución las aplicaciones .NET Core multiplataforma. También se admiten lenguajes adicionales además de C#, como JavaScript, F# y Java. Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida. Las funciones creadas como proyectos independientes se pueden implementar con funcionalidades y compatibilidad completas con la plataforma.

Para más información, consulte la [documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Comparación entre Functions v1 y v2

Hay dos versiones del entorno de ejecución de Azure Functions: 1.x y 2.x. La versión 1.x está disponible con carácter general (GA). Admite el desarrollo con .NET desde el portal o desde máquinas Windows y usa .NET Framework. La versión 1.x admite C#, JavaScript y F#, con compatibilidad experimental con Python, PHP, TypeScript, Batch, Bash y PowerShell.

[La versión 2.x también está ya disponible con carácter general](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). Aprovecha .NET Core y admite el desarrollo multiplataforma en máquinas Windows, macOS y Linux. La versión 2.x agrega compatibilidad de primera clase con Java, pero aún no admite directamente ninguno de los lenguajes experimentales. La versión 2.x usa un nuevo modelo de extensibilidad de enlaces que permite extensiones de terceros en la plataforma, control de versiones independiente de los enlaces y un entorno de ejecución más sencillo.

> **Hay un problema conocido en la versión 1.x con la [compatibilidad con la redirección de enlaces](https://github.com/Azure/azure-functions-host/issues/992).** El problema es específico del desarrollo en .NET. Los proyectos con dependencias en bibliotecas que tienen una versión diferente de las bibliotecas incluidas en el entorno de ejecución se ven afectados. El equipo de Functions se ha comprometido a realizar avances concretos para solucionar el problema. El equipo abordará la redirección de enlaces en la versión 2.x antes de que pase a estar disponible con carácter general. La declaración oficial del equipo con las correcciones y soluciones recomendadas está disponible aquí: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions) (Resolución de ensamblados en Azure Functions).

Para más información, consulte [Comparación entre 1.x y 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Compatibilidad con lenguajes de programación

Los siguientes lenguajes son compatibles con la disponibilidad general (GA), la versión preliminar o la experimental.

|Lenguaje      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |GA          |Vista previa  |
|**JavaScript**|GA          |Vista previa  |
|**F#**        |GA          |         |
|**Java**      |            |Vista previa  |
|**Python**    |Habilitación de características|         |
|**PHP**       |Habilitación de características|         |
|**TypeScript**|Habilitación de características|         |
|**Batch**     |Habilitación de características|         |
|**Bash**      |Habilitación de características|         |
|**PowerShell**|Habilitación de características|         |

Para más información, consulte [Lenguajes admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Planes de App Service

Las funciones están respaldadas por un *plan de App Service*. El plan define los recursos que usa la aplicación de funciones. Puede asignar planes a una región, determinar el tamaño y el número de máquinas virtuales que se usarán y elegir un plan de tarifa. Para un enfoque sin servidor auténtico, las aplicaciones de funciones pueden usar el plan de **consumo**. El plan de consumo escalará automáticamente el back-end en función de la carga.

Para más información, consulte [Planes de App Service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Crear su primera función

Existen tres formas comunes de crear aplicaciones de funciones.

- Hacer scripting de funciones en el portal.
- Cree los recursos necesarios con la CLI de Azure.
- Crear las funciones localmente mediante su entorno de desarrollo integrado favorito y publicarlas en Azure.

Para más información sobre la creación de una función con scripts en el portal, consulte [Creación de su primera función en Azure Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Para compilar desde la CLI de Azure, consulte [Creación de su primera función con la CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Para crear una función desde Visual Studio, consulte [Creación de la primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Descripción de los desencadenadores y enlaces

Un *desencadenador* invoca las funciones y solo pueden tener uno. Además de invocar la función, algunos desencadenadores también sirven como enlaces. También puede definir varios enlaces además del desencadenador. Los *enlaces* proporcionan una manera declarativa de conectar los datos al código. Se pueden pasar (entrada) o recibir datos (salida). Los desencadenadores y enlaces facilitan el trabajo con las funciones. Los enlaces eliminan la sobrecarga que supone crear manualmente las conexiones de la base de datos o del sistema de archivos. Toda la información necesaria para los enlaces está contenida en un archivo especial *functions.json* para scripts o se declara con atributos en el código.

Algunos desencadenadores comunes son:

- Blob Storage: se invoca la función cuando se carga o se cambia un archivo o una carpeta en el almacenamiento.
- HTTP: se invoca la función como una API REST.
- Queue: se invoca la función cuando existen elementos en una cola.
- Timer: se invoca la función según una cadencia regular.

Entre los ejemplos de enlaces se incluyen:

- CosmosDB: conéctese fácilmente a la base de datos para cargar o guardar archivos.
- Table Storage: trabaje con el almacenamiento de clave-valor de la aplicación de funciones.
- Queue Storage: recupere fácilmente elementos de una cola o coloque otros nuevos en ella.

En el siguiente archivo *functions.json* de ejemplo se define un desencadenador y un enlace:

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

En este ejemplo, la función se desencadena mediante un cambio en Blob Storage en el contenedor `images`. La información del archivo se pasa, por lo que el desencadenador también actúa como un enlace. Existe otro enlace para colocar la información en una cola denominada `images`.

Este es el script en C# de la función:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

El ejemplo es una función simple que toma el nombre del archivo que se modificó o cargó en Blob Storage y lo coloca en una cola para su procesamiento posterior.

Para obtener una lista completa de los desencadenadores y enlaces, consulte [Conceptos básicos sobre los enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Servidores proxy

Los servidores proxy proporcionan funcionalidad de redirección para la aplicación. Los servidores proxy exponen un punto de conexión y lo asignan a otro recurso. Con servidores proxy, puede:

- Volver a enrutar una solicitud entrante a otro punto de conexión.
- Modificar la solicitud entrante antes de que se pase.
- Modificar o proporcionar una respuesta.

Los servidores proxy se usan para escenarios como:

- Simplificación, acortamiento o cambio de la dirección URL.
- Proporcionar un prefijo de API coherente para varios servicios de back-end.
- Simulación de una respuesta a un punto de conexión que se está desarrollando.
- Proporcionar una respuesta estática a un punto de conexión conocido.
- Mantener la coherencia de un punto de conexión de API mientras se mueve o migra el back-end.

Los servidores proxy se almacenan como definiciones de JSON. A continuación se muestra un ejemplo:

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

El proxy `Domain Redirect` toma una ruta abreviada y la asigna a un recurso de función más largo. La transformación tiene el siguiente aspecto:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

El proxy `Root` toma todo lo que se envía a la dirección URL raíz (`https://--shorturl--/`) y lo redirige al sitio de documentación.

Aparece un ejemplo del uso de servidores proxy en el vídeo [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102) (Migración de aplicaciones a la nube con Azure Functions sin servidor). En tiempo real, una aplicación ASP.NET Core que se ejecuta en el servidor SQL Server local se migra a la nube de Azure. Los servidores proxy se usan para ayudar a refactorizar un proyecto de API web tradicional para que utilice funciones.

Para más información sobre servidores proxy, consulte [Uso de Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Anterior](azure-serverless-platform.md)
>[Siguiente](application-insights.md)
