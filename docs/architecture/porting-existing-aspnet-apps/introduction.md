---
title: Introducción a la migración de aplicaciones a .NET Core
description: En este capítulo se describe una lista de consideraciones para los equipos que consideran la migración de aplicaciones de ASP.NET existentes a .NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a346d1c693389cc4ca682b41a3b7fc094cfa5482
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401488"
---
# <a name="introduction-to-porting-apps-to-net-core"></a>Introducción a la migración de aplicaciones a .NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

.NET Core es un paso revolucionario hacia adelante desde .NET Framework. Ofrece un host de ventajas con respecto a .NET Framework en todo el tablero, desde la productividad hasta el rendimiento, desde el soporte multiplataforma hasta la satisfacción del desarrollador. ASP.NET Core ha votado incluso el marco de trabajo web más querido en la [encuesta del desarrollador de 2020 Stack Overflow](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks). Claramente hay razones importantes que se deben tener en cuenta para la migración.

Es importante tener en cuenta que [.net Core es el futuro de .net](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/). Para citar este artículo:

> Las nuevas aplicaciones deben compilarse en .NET Core. .NET Core es donde se producirán inversiones futuras en .NET. Las aplicaciones existentes pueden permanecer en .NET Framework que se admitirán. Las aplicaciones existentes que quieran aprovechar las nuevas características de .NET deben considerar la posibilidad de pasar a .NET Core. A medida que planeamos en el futuro, se incorporarán más capacidades a la plataforma.

Sin embargo, la actualización de la aplicación a ASP.NET Core requerirá algún esfuerzo. Ese esfuerzo se debe equilibrar con respecto al valor y los objetivos empresariales. .NET Framework aplicaciones tienen una larga duración, con compatibilidad integrada en Windows para el futuro previsible. ¿Cuáles son algunas de las preguntas que debe tener en cuenta antes de decidir la migración a .NET Core? ¿Cuáles son las ventajas previstas? ¿Cuáles son los inconvenientes? ¿Cuánto esfuerzo está implicado? Estas preguntas obvias son solo el principio, pero conviene que un punto de partida excelente a medida que los equipos consideren la posibilidad de admitir las necesidades de sus clientes con las aplicaciones actuales y futuras.

- ¿Es adecuada la migración a .NET Core?
- ¿Cuándo tiene sentido permanecer en .NET Framework?
- ¿Las aplicaciones deben tener como destino ASP.NET Core 2,1 como una piedra de paso?
- ¿Cómo deberían los equipos elegir la versión correcta de .NET Core para el destino?
- ¿Qué estrategias se recomiendan para la migración incremental de aplicaciones de gran tamaño?
- ¿Qué estrategias de implementación se deben tener en cuenta al migrar a .NET Core?
- ¿Dónde podemos encontrar recursos adicionales?

En este capítulo introductorio se abordan todas estas preguntas y otras más antes de pasar a consideraciones más específicas y técnicas en los próximos capítulos.

## <a name="references"></a>Referencias

- [2020 Stack Overflow Marcos Web más queridos de la encuesta para desarrolladores](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks)
- [.NET Core es el futuro de .NET](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/)

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](migration-considerations.md)
