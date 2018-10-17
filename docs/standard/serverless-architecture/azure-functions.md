---
title: 'Funciones de Azure: aplicaciones sin servidor'
description: Las funciones de Azure proporcionan funcionalidades sin servidor en varios idiomas (C#, en JavaScript, Java) y plataformas para proporcionar controlado por eventos instantánea escalar código.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: f08ba20b485197acd3bb5cdfe5699cd6be991d7c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "49370193"
---
# <a name="azure-functions"></a>Comprobación de

Azure functions proporciona una experiencia de proceso sin servidor. Invoca una función de un *desencadenador* (por ejemplo, el acceso a un punto de conexión HTTP o un temporizador) y ejecuta un bloque de código o la lógica empresarial. Las funciones también soporte técnico especializado *enlaces* que se conectan a recursos como almacenamiento y colas.

![Logotipo de Azure functions](./media/azure-functions-logo.png)

Hay dos versiones de framework de Azure Functions. La versión heredada es compatible con la versión completa de .NET Framework y el nuevo tiempo de ejecución es compatible con aplicaciones de .NET Core multiplataforma. Compatibilidad para idiomas adicionales además de C#, como JavaScript, F # y Java. Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida. Las funciones que se crean como proyectos independientes pueden implementarse con capacidades y compatibilidad de plataforma completa.

Para obtener más información, consulte [documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Funciones v1 y v2

Hay dos versiones del runtime de Azure Functions: 1.x y 2.x. Versión 1.x está disponible con carácter general (GA). Admite el desarrollo de .NET desde el portal o las máquinas Windows y usa .NET Framework. 1.x es compatible con C#, JavaScript y F #, con compatibilidad experimental con Python, PHP, TypeScript, Batch, Bash y PowerShell.

Versión 2.x está en versión preliminar. Aprovecha .NET Core y admite el desarrollo multiplataforma en máquinas Linux, macOS y Windows. 2.x agrega soporte de primera clase para Java pero todavía no directamente admite cualquiera de los lenguajes experimentales. Versión 2.x usa un nuevo modelo de extensibilidad de enlace que permite a las extensiones de terceros a la plataforma, crear versiones independientes de los enlaces, y una más simplificado de entorno de ejecución.

> **Hay un problema conocido en la versión 1.x con [compatibilidad de redireccionamiento de enlace](https://github.com/Azure/azure-functions-host/issues/992).** El problema es específico para el desarrollo de. NET. Los proyectos con dependencias en las bibliotecas que son una versión diferente de las bibliotecas incluidas en el tiempo de ejecución se ven afectados. El equipo de funciones se ha comprometido a progresar concreta en el problema. El equipo abordará redirecciones de enlace en 2.x antes de que entre en disponibilidad general. La instrucción del equipo oficial con correcciones sugeridas y soluciones alternativas está disponible aquí: [resolución de ensamblado en Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Para obtener más información, consulte [comparación entre 1.x y 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Compatibilidad con lenguajes de programación

Se admiten los siguientes idiomas ya sea en general (GA), disponibilidad de una vista previa, o en fase experimental.

|Lenguaje      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |DISPONIBILIDAD GENERAL          |Vista previa  |
|**JavaScript**|DISPONIBILIDAD GENERAL          |Vista previa  |
|**F#**        |DISPONIBILIDAD GENERAL          |         |
|**Java**      |            |Vista previa  |
|**Python**    |Habilitación de características|         |
|**PHP**       |Habilitación de características|         |
|**TypeScript**|Habilitación de características|         |
|**Batch**     |Habilitación de características|         |
|**Bash**      |Habilitación de características|         |
|**PowerShell**|Habilitación de características|         |

Para obtener más información, consulte [idiomas admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Planes de App service

Las funciones están respaldadas por un *plan de app service*. El plan define los recursos utilizados por la aplicación de functions. Puede asignar los planes a una región, determinar el tamaño y el número de máquinas virtuales que se usará y elegir un plan de tarifa. Un enfoque sin servidor es true, las aplicaciones de función pueden usar el **consumo** plan. El plan de consumo escalará el back-end automáticamente según la carga.

Para obtener más información, consulte [planes de App service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Cree su primera función

Hay tres formas comunes de creación de aplicaciones de función.

* Funciones de script en el portal.
* Cree los recursos necesarios con la interfaz de línea de comandos (CLI) de Azure.
* Crear funciones localmente mediante su IDE favorito y publicarlos en Azure.

Para obtener más información sobre cómo crear una función con secuencias de comandos en el portal, consulte [crear su primera función en Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Para compilar desde la CLI de Azure, consulte [crear su primera función mediante la CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Para crear una función desde Visual Studio, consulte [crear su primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Comprender los desencadenadores y enlaces

Las funciones se invocan mediante un *desencadenador* y puede tener exactamente uno. Además de invocar la función, determinados desencadenadores también sirven como los enlaces. También puede definir varios enlaces además el desencadenador. *Enlaces* proporcionan una forma declarativa para conectar datos a su código. Se pueden pasar en (entrada) o recibir datos (output). Hacen funciones facilita el trabajo con desencadenadores y enlaces. Enlaces de quitar la sobrecarga de la creación manual de base de datos o archivo del sistema conexiones. Toda la información necesaria para los enlaces está contenida en un especial *functions.json* de archivos para las secuencias de comandos o declarados con atributos en el código.

Algunos desencadenadores comunes incluyen:

* Almacenamiento de blobs: invocar la función cuando se carga o se puede cambiar en el almacenamiento de un archivo o carpeta.
* HTTP: invocar la función como una API de REST.
* Cola: invocar la función cuando existen elementos en una cola.
* Temporizador: invocar la función a un ritmo normal.

Ejemplos de enlaces:

* COSMOS DB: conectar fácilmente a la base de datos para cargar o guardar archivos.
* Almacenamiento de tabla: trabajar con almacenamiento de pares clave-valor de la aplicación de función.
* Almacenamiento en cola: fácilmente recuperar elementos de una cola o colocar los nuevos elementos en la cola.

En el siguiente ejemplo *functions.json* archivo define un desencadenador y un enlace:

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

En este ejemplo, la función se desencadena por un cambio en el almacenamiento de blobs en el `images` contenedor. La información del archivo se pasa, por lo que el desencadenador también actúa como un enlace. Existe otro enlace para introducir la información en una cola denominada `images`.

Este es el script de C# para la función:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

El ejemplo es una función simple que toma el nombre del archivo que se modificó o carga en el almacenamiento de blobs y lo coloca en una cola para su posterior procesamiento.

Para obtener una lista completa de los desencadenadores y enlaces, vea [conceptos de enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Servidores proxy

Los proxies proporcionan funcionalidad de redirección para la aplicación. Los proxies exponen un punto de conexión y asignan ese extremo a otro recurso. Con los servidores proxy, puede:

* Volver a enrutar una solicitud entrante a otro punto de conexión.
* Modifique la solicitud entrante antes de pasarlo a lo largo.
* Modificar o proporcionar una respuesta.

Los servidores proxy se utilizan para escenarios como:

* Simplificar, lo que reduce o cambiar la dirección URL.
* Proporcionar un prefijo de API coherente a varios servicios de back-end.
* Una respuesta a un punto de conexión que se desarrolla la simulación.
* Proporcionar una respuesta estática a un extremo conocido.
* Mantener un punto de conexión de API coherente mientras se mueve o se migró el back-end.

Los servidores proxy se almacenan como definiciones de JSON. A continuación, se muestra un ejemplo:

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

El `Domain Redirect` proxy toma una ruta abreviada y lo asigna al recurso de función más largo. La transformación es similar:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

El `Root` proxy toma todo lo envía a la dirección URL raíz (`https://--shorturl--/`) y lo redirige a la documentación del sitio.

Se muestra un ejemplo del uso de los servidores proxy en el vídeo [Azure: traiga su aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/events/Connect/2017/E102). En tiempo real, se migra una aplicación de ASP.NET Core que se ejecutan en el servidor SQL Server local a la nube de Azure. Los servidores proxy se utilizan para ayudar a refactorizar un proyecto de API Web tradicional para usar las funciones.

Para obtener más información acerca de los servidores proxy, consulte [trabajar con Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
[Anterior](azure-serverless-platform.md)
[Siguiente](application-insights.md)