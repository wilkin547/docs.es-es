---
title: Aplicaciones sin servidor Azure Functions
description: Azure Functions proporciona funcionalidades sin servidor a través deC#varios lenguajes (, JavaScript, Java) y plataformas para proporcionar código de escalado instantáneo orientado a eventos.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5e8187b3752a0f0d0bcf8e15f2ce440dc5a64e45
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522867"
---
# <a name="azure-functions"></a>Comprobación de

Azure Functions proporciona una experiencia de proceso sin servidor. Un *desencadenador* invoca una función (como el acceso a un punto de conexión http o un temporizador) y ejecuta un bloque de código o lógica de negocios. Las funciones también admiten *enlaces* especializados que se conectan a recursos como almacenamiento y colas.

![Logotipo de Azure Functions](./media/azure-functions-logo.png)

Hay dos versiones de Azure Functions Framework. La versión heredada es compatible con el .NET Framework completo y el nuevo Runtime es compatible con las aplicaciones .NET Core multiplataforma. Se admiten C# lenguajes adicionales, F#además de JavaScript, y Java. Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida. Las funciones creadas como proyectos independientes se pueden implementar con capacidades y soporte técnico completo de la plataforma.

Para obtener más información, consulte la [documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Funciones v1 frente a V2

Hay dos versiones del tiempo de ejecución de Azure Functions: 1. x y 2. x. La versión 1. x está disponible con carácter general (GA). Admite el desarrollo de .NET desde el portal o las máquinas de Windows y usa el .NET Framework. 1. x admite C#, JavaScript y F#, con compatibilidad experimental con Python, PHP, TypeScript, Batch, bash y PowerShell.

La [versión 2. x también está disponible con carácter general](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). Aprovecha .NET Core y admite el desarrollo multiplataforma en máquinas Windows, macOS y Linux. 2. x agrega compatibilidad de primera clase para Java, pero aún no es compatible directamente con ninguno de los lenguajes experimentales. La versión 2. x usa un nuevo modelo de extensibilidad de enlaces que permite extensiones de terceros a la plataforma, control de versiones independiente de los enlaces y un entorno de ejecución más sencillo.

> **Hay un problema conocido en 1. x con compatibilidad con la [redirección de enlaces](https://github.com/Azure/azure-functions-host/issues/992).** El problema es específico del desarrollo de .NET. Los proyectos con dependencias en bibliotecas que tienen una versión diferente de las bibliotecas incluidas en el tiempo de ejecución se ven afectados. El equipo de funciones se ha confirmado para hacer un progreso concreto del problema. El equipo tratará las redirecciones de enlace en 2. x antes de que pase a la disponibilidad general. La declaración oficial del equipo con correcciones y soluciones recomendadas está disponible aquí: [resolución de ensamblados en Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Para obtener más información, vea [Compare 1. x y 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Compatibilidad con el lenguaje de programación

Los siguientes idiomas son compatibles con la disponibilidad general (GA), la versión preliminar o el experimental.

|Lenguaje      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |General          |Vista previa  |
|**JavaScript**|General          |Vista previa  |
|**F#**        |General          |         |
|**Java**      |            |Vista previa  |
|**Python**    |Habilitación de características|         |
|**PHP**       |Habilitación de características|         |
|**TypeScript**|Habilitación de características|         |
|**Batch**     |Habilitación de características|         |
|**Sucesión**      |Habilitación de características|         |
|**PowerShell**|Habilitación de características|         |

Para obtener más información, consulte [idiomas admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Planes de App Service

Las funciones están respaldadas por un *plan de App Service*. El plan define los recursos usados por la aplicación de functions. Puede asignar planes a una región, determinar el tamaño y el número de máquinas virtuales que se usarán y elegir un plan de tarifa. Para un enfoque real sin servidor, las aplicaciones de función pueden usar el plan de **consumo** . El plan de consumo escalará automáticamente el back-end en función de la carga.

Para obtener más información, consulte [planes de App Service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Creación de la primera función

Existen tres formas comunes de crear aplicaciones de función.

- Funciones de script en el portal.
- Cree los recursos necesarios mediante la interfaz de la línea de comandos (CLI) de Azure.
- Cree funciones localmente mediante su IDE favorito y publíquelos en Azure.

Para obtener más información sobre la creación de una función con scripts en el portal, consulte Creación de la [primera función en el Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Para compilar desde el CLI de Azure, consulte [crear la primera función mediante el CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Para crear una función desde Visual Studio, consulte [crear la primera función con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Descripción de los desencadenadores y los enlaces

Las funciones se invocan mediante un *desencadenador* y pueden tener exactamente una. Además de invocar la función, algunos desencadenadores también sirven como enlaces. También puede definir varios enlaces además del desencadenador. Los *enlaces* proporcionan una manera declarativa de conectar los datos al código. Se pueden pasar (entrada) o recibir datos (salida). Los desencadenadores y los enlaces facilitan el trabajo con las funciones. Los enlaces quitan la sobrecarga de crear manualmente las conexiones de base de datos o del sistema de archivos. Toda la información necesaria para los enlaces está contenida en un archivo *functions. JSON* especial para scripts o declarado con atributos en el código.

Algunos desencadenadores comunes son:

- Blob Storage: invocar la función cuando se carga o se cambia un archivo o una carpeta en el almacenamiento.
- HTTP: invocar la función como una API de REST.
- Queue: invoca la función cuando existen elementos en una cola.
- Temporizador: invoque la función a una cadencia regular.

Entre los ejemplos de enlaces se incluyen:

- CosmosDB: Conéctese fácilmente a la base de datos para cargar o guardar archivos.
- Table Storage: trabaje con el almacenamiento de clave y valor de la aplicación de función.
- Queue Storage: recuperar fácilmente los elementos de una cola o colocar nuevos elementos en la cola.

En el ejemplo siguiente, el archivo *functions. JSON* define un desencadenador y un enlace:

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

En este ejemplo, la función se desencadena mediante un cambio en el almacenamiento de blobs en el contenedor `images`. La información del archivo se pasa, por lo que el desencadenador también actúa como un enlace. Existe otro enlace para colocar información en una cola denominada `images`.

Este es el C# script de la función:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

El ejemplo es una función simple que toma el nombre del archivo que se modificó o cargó en el almacenamiento de blobs y lo coloca en una cola para su procesamiento posterior.

Para obtener una lista completa de los desencadenadores y enlaces, vea [Azure Functions conceptos de desencadenadores y enlaces](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Servidores proxy

Los servidores proxy proporcionan funcionalidad de redirección para la aplicación. Los servidores proxy exponen un punto de conexión y lo asignan a otro recurso. Con servidores proxy, puede:

- Reenruta una solicitud entrante a otro punto de conexión.
- Modifique la solicitud entrante antes de que se pase.
- Modifique o proporcione una respuesta.

Los servidores proxy se utilizan para escenarios como los siguientes:

- Simplificar, acortar o cambiar la dirección URL.
- Proporcionar un prefijo de API coherente a varios servicios back-end.
- Simular una respuesta a un extremo que se está desarrollando.
- Proporcionar una respuesta estática a un punto de conexión conocido.
- Mantener un punto de conexión de API coherente mientras se mueve o migra el back-end.

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

El proxy `Domain Redirect` toma una ruta abreviada y la asigna al recurso de función más largo. La transformación tiene el siguiente aspecto:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

El proxy `Root` toma todo lo que se envía a la dirección URL raíz (`https://--shorturl--/`) y lo redirige al sitio de documentación.

Un ejemplo del uso de servidores proxy se muestra en el vídeo [Azure: traer la aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/events/Connect/2017/E102). En tiempo real, una aplicación ASP.NET Core que se ejecuta en el SQL Server local se migra a la nube de Azure. Los proxies se usan para ayudar a refactorizar un proyecto de API Web tradicional para usar las funciones.

Para obtener más información acerca de los servidores proxy, consulte [trabajar con Azure Functions proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Anterior](azure-serverless-platform.md)
>[Siguiente](application-insights.md)
