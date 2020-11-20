---
title: 'Azure Functions: Aplicaciones sin servidor'
description: Azure Functions proporciona funcionalidades sin servidor mediante varios lenguajes (C#, JavaScript, Java) y plataformas para proporcionar código de escalado instantáneo orientado a eventos.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 08e1aaecdee753dc25cca0d6356caaafae1ad510
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557121"
---
# <a name="azure-functions"></a>Comprobación de

Azure Functions proporciona una experiencia de proceso sin servidor. Un *desencadenador* invoca una función (por ejemplo, el acceso a un punto de conexión HTTP o un temporizador) y ejecuta un bloque de código o lógica de negocios. Las funciones también admiten *enlaces* especializados que se conectan a recursos como los de almacenamiento y colas.

![Logotipo de Azure Functions](./media/azure-functions-logo.png)

La versión del entorno de ejecución actual 3.0 es compatible con aplicaciones de .NET Core 3.1 multiplataforma. También se admiten lenguajes adicionales además de C#, como JavaScript, F# y Java. Las funciones creadas en el portal proporcionan una sintaxis de scripting enriquecida. Las funciones creadas como proyectos independientes se pueden implementar con funcionalidades y compatibilidad completas con la plataforma.

Para más información, consulte la [documentación de Azure Functions](/azure/azure-functions).

## <a name="programming-language-support"></a>Compatibilidad con lenguajes de programación

Todos los siguientes idiomas se admiten en la disponibilidad general (GA).

|Lenguaje      |Entornos de ejecución admitidos|
|--------------|------------------|
|**C#**        |.NET Core 3.1     |
|**JavaScript**|Nodo 10 y 12      |
|**F#**        |.NET Core 3.1     |
|**Java**      |Java 8            |
|**Python**    |Python 3.6, 3.7 y 3.8|
|**TypeScript**|Nodo 10 y 12 (mediante JavaScript)|
|**PowerShell**|PowerShell Core 6|

Para más información, consulte [Lenguajes admitidos](/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Planes de App Service

Las funciones están respaldadas por un *plan de App Service*. El plan define los recursos que usa la aplicación de funciones. Puede asignar planes a una región, determinar el tamaño y el número de máquinas virtuales que se usarán y elegir un plan de tarifa. Para un enfoque sin servidor auténtico, las aplicaciones de funciones pueden usar el plan de **consumo**. El plan de consumo escalará automáticamente el back-end en función de la carga.

Otra opción de hospedaje para las aplicaciones de función es el [plan Premium](/azure/azure-functions/functions-premium-plan). Este plan proporciona una instancia siempre activada para evitar el inicio en frío, admite características avanzadas como la conectividad de VNet y se ejecuta en hardware premium.

Para más información, consulte [Planes de App Service](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Crear su primera función

Existen tres formas comunes de crear aplicaciones de funciones.

- Hacer scripting de funciones en el portal.
- Cree los recursos necesarios con la CLI de Azure.
- Crear las funciones localmente mediante su entorno de desarrollo integrado favorito y publicarlas en Azure.

Para más información sobre la creación de una función con scripts en el portal, consulte [Creación de su primera función en Azure Portal](/azure/azure-functions/functions-create-first-azure-function).

Para compilar desde la CLI de Azure, consulte [Creación de su primera función con la CLI de Azure](/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Para crear una función desde Visual Studio, consulte [Creación de la primera función mediante Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).

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

Para obtener una lista completa de los desencadenadores y enlaces, consulte [Conceptos básicos sobre los enlaces y desencadenadores de Azure Functions](/azure/azure-functions/functions-triggers-bindings).

>[!div class="step-by-step"]
>[Anterior](azure-serverless-platform.md)
>[Siguiente](application-insights.md)
