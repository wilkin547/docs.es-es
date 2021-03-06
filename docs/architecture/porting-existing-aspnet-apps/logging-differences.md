---
title: Diferencias de registro entre ASP.NET MVC y ASP.NET Core
description: ¿Cómo es el registro diferente entre ASP.NET MVC y aplicaciones de API Web y aplicaciones ASP.NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 0ad12463c8d13d13516ab027e56f809b67f713e4
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401737"
---
# <a name="logging-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de registro entre ASP.NET MVC y ASP.NET Core

El registro de aplicaciones proporciona información de diagnóstico importante, especialmente para las aplicaciones que se ejecutan en producción. ASP.NET Core introduce un nuevo sistema para agregar el registro estandarizado a cualquier aplicación. Las aplicaciones de ASP.NET MVC y Web API existentes tienen más probabilidades de usar soluciones de registro de terceros, que probablemente sigan siendo compatibles con ASP.NET Core.

## <a name="aspnet-mvc-logging"></a>Registro de ASP.NET MVC

No hay ninguna solución de registro integrada en las aplicaciones de ASP.NET MVC y Web API. En su lugar, la mayoría de las aplicaciones usan soluciones de registro de terceros como [log4net](https://www.nuget.org/packages/log4net/), [NLog](https://www.nuget.org/packages/NLog/)o [Serilog](https://www.nuget.org/packages/Serilog). Muchos equipos también optan por lanzar su propia solución de registro. Los marcos de registro suelen admitir varios "receptores" (o destinos o anexadores) para la salida del registro, como archivos de texto, bases de datos o incluso correos electrónicos. Utilizan la configuración para determinar qué niveles de mensajes de registro desde qué partes del sistema se enrutan a distintos receptores. Al considerar cómo migrar el registro de una aplicación a .NET Core, revise cómo se realiza el registro y cómo se [configura](configuration-differences.md) en la aplicación.

## <a name="aspnet-core-logging"></a>Registro de ASP.NET Core

En ASP.NET Core, el [registro es una característica integrada](/aspnet/core/fundamentals/logging/) que se puede configurar y ampliar cuando se inicia la aplicación. Los registradores de terceros, incluidos los mencionados anteriormente, se pueden integrar con ASP.NET Core para mejorar su funcionalidad.

El registro de ASP.NET Core utiliza categorías y niveles para controlar lo que se registra y cómo. Las clases suelen usar instancias de la `ILogger<T>` interfaz, con el tipo de clase usado como `T` tipo genérico. En este escenario, el nombre completo de la clase se usa como categoría. Los registradores también se pueden crear con una categoría personalizada mediante `ILoggerFactory` . Los niveles de registro van desde el más detallado, `Trace` hasta el más importante `Critical` . Mediante la configuración, las aplicaciones pueden especificar el nivel mínimo de registro que debe incluirse en cada categoría (con caracteres comodín).

Una configuración de registro típica podría registrar `Information` y por encima de la información de forma predeterminada, pero solo `Warning` o por encima de las `Microsoft` categorías prefijas:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning"
    }
  }
}
```

La compatibilidad con el inicio de sesión ASP.NET Core es amplia y flexible. Para obtener información más detallada, [consulte los documentos](/aspnet/core/fundamentals/logging/).

## <a name="migrate-logging"></a>Migración del registro

La forma de migrar el registro de la aplicación de .NET Framework a .NET Core depende de cómo se registre la aplicación ahora. Si usa un paquete NuGet de terceros, consulte la documentación de actualización de ese paquete. Lo más probable es que la ruta de actualización sea bastante sencilla. Si utiliza su propia solución de registro, realice una de las siguientes acciones:

1. Migración de la solución de registro
1. Migrar a una solución de registro de otro fabricante
1. Usar la compatibilidad de registro integrada en ASP.NET Core

Puede hacer referencia al `Microsoft.Extensions.Logging` paquete desde .NET Framework aplicaciones, siempre y cuando use NuGet 4,3 o posterior y estén en .NET Framework 4.6.1 o posterior. Una vez que la aplicación hace referencia a este paquete, puede convertir las instrucciones de registro para que usen las nuevas extensiones antes de migrar la aplicación a .NET Core. Esto puede proporcionar una piedra de paso hacia la migración completa, ya que la aplicación puede seguir ejecutándose en .NET Framework mientras se registra con el paquete de extensiones más reciente.

## <a name="references"></a>Referencias

- [Registros en .NET Core y ASP.NET Core](/aspnet/core/fundamentals/logging/)
- [Paquete NuGet Microsoft. Extensions. Logging](https://www.nuget.org/packages/microsoft.extensions.logging/)

>[!div class="step-by-step"]
>[Anterior](middleware-modules-handlers.md)
>[Siguiente](routing-differences.md)
