---
title: Estrategias para migrar incrementalmente
description: ¿Qué estrategias pueden adoptar los equipos que les permitirán migrar aplicaciones de gran tamaño de ASP.NET MVC a .NET Core de forma incremental?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: dc500fa71188c472f78ef4df95d79434208552c3
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401887"
---
# <a name="strategies-for-migrating-incrementally"></a>Estrategias para migrar incrementalmente

El mayor desafío con la migración de cualquier aplicación grande es determinar cómo dividir el proceso en tareas más pequeñas. Hay varias estrategias que se pueden aplicar a este propósito, como dividir la aplicación en capas horizontales como la interfaz de usuario, el acceso a datos, la lógica de negocios o dividir la aplicación en aplicaciones independientes y más pequeñas. Otra estrategia es actualizar algunas o todas las aplicaciones a diferentes versiones de .NET Framework en una versión reciente de .NET Core. Un enfoque que puede usar es migrar [segmentos verticales](https://deviq.com/practices/vertical-slices) de la aplicación, en lugar de intentar migrar una capa horizontal a la vez. Veamos cada uno de estos enfoques diferentes.

Tenga en cuenta el reto de migrar una aplicación grande de ASP.NET 4,5. Un enfoque consiste en migrar toda la aplicación directamente desde .NET Framework 4,5 a .NET Core 3,1. Sin embargo, este enfoque debe tener en cuenta todos los cambios importantes entre los dos marcos y versiones, que son importantes.

## <a name="migrating-layer-by-layer"></a>Migrar capa por nivel

Se [.net Standard](https://dotnet.microsoft.com/platform/dotnet-standard)una adición reciente al ecosistema de .net que ayuda a la interoperabilidad entre diferentes .NET Framework. .NET Standard permite que las bibliotecas se compilan en el conjunto acordado de API comunes, asegurándose de que se pueden usar en cualquier aplicación .NET. .NET Standard 2,0 es importante porque abarca la mayoría de la funcionalidad de la biblioteca de clases base que utilizan la mayoría de las aplicaciones de .NET Framework y .NET Core. Desafortunadamente, la versión más antigua de .NET compatible con .NET Standard 2,0 es .NET Framework 4.6.1 y hay una serie de actualizaciones en .NET Framework 4,8 que lo convierten en una opción atractiva para las actualizaciones iniciales.

Un enfoque para actualizar de forma incremental un sistema .NET Framework 4,5 de nivel por nivel es actualizar primero sus dependencias de la biblioteca de clases a .NET Framework 4,8. A continuación, modifique estas bibliotecas para que sean .NET Standard bibliotecas de clases. Use la compilación condicional y de compatibilidad con múltiples versiones, si es necesario. Este paso puede ser útil en escenarios donde las dependencias de la aplicación requieren .NET Framework y no se pueden migrar fácilmente directamente para usar .NET Standard y .NET Core. Como las bibliotecas de .NET Framework pueden usarse en aplicaciones de ASP.NET Core 2,1, el siguiente paso es migrar la funcionalidad web de la aplicación a ASP.NET Core 2,1 (como se describe en el [capítulo anterior](choose-net-core-version.md)). Se trata de un enfoque "inferior hacia arriba", que comienza con las dependencias de la biblioteca de clases de bajo nivel y trabaja hasta el punto de entrada de la aplicación Web.

Una vez que la aplicación se ejecuta en ASP.NET Core 2,1, la migración a ASP.NET Core 3,1 en el aislamiento es relativamente sencilla. El desafío más probable de este paso es actualizar las dependencias incompatibles para admitir .NET Core y, posiblemente, versiones superiores de .NET Standard. En el caso de las aplicaciones que no tienen dependencias problemáticas en bibliotecas solo de .NET Framework, hay poca razón para actualizar a ASP.NET Core 2,1. Migrar directamente a ASP.NET Core 3,1 tiene más sentido y requiere menos esfuerzo.

En el momento en que la aplicación se ejecuta en .NET Core 3,1, la migración a la versión actual de .NET 5 es relativamente sencilla. El proceso implica principalmente actualizar el marco de trabajo de destino de los archivos de proyecto y sus dependencias de paquetes NuGet asociadas. Aunque se deben [tener en cuenta varios cambios importantes](../../core/compatibility/5.0.md), la mayoría de las aplicaciones no requieren modificaciones significativas para pasar de .net Core 3,1 a .net 5. Lo más probable es que el factor decisivo [para elegir entre .net Core 3,1 y .net 5 sea compatible](choose-net-core-version.md).

En lugar de un enfoque "inferior", otra alternativa es comenzar con la aplicación web (o incluso con toda la solución) y usar una herramienta automatizada para ayudarle con la actualización. La [herramienta del Asistente para actualización de .net](https://aka.ms/dotnet-upgrade-assistant) se puede usar para ayudar a actualizar .NET Framework aplicaciones a .net Core/.net 5. Automatiza muchas de las tareas comunes relacionadas con la actualización de aplicaciones, como la modificación del formato de archivo del proyecto, la configuración de las plataformas de destino adecuadas, la actualización de las dependencias de NuGet, etc.

En lugar de un enfoque "inferior", otra alternativa es comenzar con la aplicación web (o incluso con toda la solución) y usar una herramienta automatizada para ayudarle con la actualización. La [herramienta del Asistente para actualización de .net](https://aka.ms/dotnet-upgrade-assistant) se puede usar para ayudar a actualizar .NET Framework aplicaciones a .net Core/.net 5. Automatiza muchas de las tareas comunes relacionadas con la actualización de aplicaciones, como la modificación del formato de archivo del proyecto, la configuración de las plataformas de destino adecuadas, la actualización de las dependencias de NuGet, etc.

## <a name="migrating-slice-by-slice"></a>Migrando segmento por segmento

Otro enfoque de la migración sería identificar los segmentos verticales de funcionalidad y migrarlos a la plataforma de destino uno a uno. El primer paso sería crear una nueva ASP.NET Core aplicación 3,1 o 5. A continuación, identifique la página o el punto de conexión de API individual que se migrará primero. Cree solo la funcionalidad necesaria para admitir esta ruta en la aplicación ASP.NET Core. A continuación, use la reescritura HTTP y/o un proxy inverso para empezar a enviar solicitudes para estas páginas o puntos de conexión a la nueva aplicación en lugar de a la aplicación ASP.NET.

En el [capítulo 5, escenarios de implementación,](deployment-scenarios.md)se explican algunas instrucciones específicas sobre cómo seguir esta estrategia con IIS.

## <a name="references"></a>Referencias

- [¿Qué es .NET Standard?](https://dotnet.microsoft.com/platform/dotnet-standard)
- [Presentación de .NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/)
- [Migrar de ASP.NET Core 3,1 a 5,0](/aspnet/core/migration/31-to-50)
- [Herramienta del Asistente para actualización de .NET](https://aka.ms/dotnet-upgrade-assistant)

>[!div class="step-by-step"]
>[Anterior](choose-net-core-version.md)
>[Siguiente](migrate-web-forms.md)
