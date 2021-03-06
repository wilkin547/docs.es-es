---
title: Estrategias para migrar aplicaciones de ASP.NET Web Forms
description: ¿Qué estrategias pueden usar los equipos para migrar aplicaciones de formularios Web Forms de ASP.NET a .NET Core?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 0b37a37f047de50c347313be14a2228838da6995
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401537"
---
# <a name="strategies-for-migrating-aspnet-web-forms-apps"></a>Estrategias para migrar aplicaciones de ASP.NET Web Forms

En este libro se proporcionan instrucciones para migrar aplicaciones grandes de ASP.NET MVC y API Web a .NET Core. Algunas de estas aplicaciones ASP.NET también pueden incluir páginas de formularios Web Forms (*. aspx*) que deben solucionarse. Los formularios Web Forms de ASP.NET no se admiten en .NET Core (ni ASP.NET Web Pages). Normalmente, la funcionalidad de estas páginas se debe volver a escribir al migrar a ASP.NET Core. Sin embargo, hay algunas estrategias que puede aplicar antes o durante la migración para ayudar a reducir el esfuerzo general necesario.

Los formularios Web Forms seguirán siendo compatibles durante bastante tiempo. Una opción puede ser mantener esta funcionalidad en una aplicación ASP.NET 4. x.

## <a name="separate-business-logic-and-other-concerns"></a>Separe la lógica de negocios y otros problemas

Cuanto menor sea el código de las páginas de formularios Web Forms de ASP.NET, mejor. Cuando sea posible, mantenga la lógica de negocios y otros problemas como el acceso a datos en clases independientes, idealmente en bibliotecas de clases independientes. Estas bibliotecas de clases se pueden migrar a .NET Standard y usar cualquier aplicación ASP.NET Core.

## <a name="implement-client-behavior-and-web-apis"></a>Implementar el comportamiento del cliente y las API Web

Considere la posibilidad de elegir entre implementar la lógica en formularios Web Forms o en el explorador con la ayuda de las llamadas de API. Dé prioridad a la última. Se admite la migración de API a ASP.NET Core. El comportamiento del lado cliente debe ser independiente de la pila del lado servidor que usa la aplicación. El uso de este enfoque tiene la ventaja adicional de proporcionar una experiencia de usuario más dinámica.

## <a name="consider-blazor"></a>Tenga en cuenta el increíble

Increíble: le permite crear interfaces de usuario Web interactivas con C# en lugar de JavaScript. Se puede ejecutar en el servidor o en el explorador mediante webassembly. Las aplicaciones de formularios Web Forms de ASP.NET se pueden migrar página a página a aplicaciones increíbles. Para obtener más información sobre cómo migrar aplicaciones de formularios Web Forms a extraordinarias, consulte el [ASP.net de los desarrolladores de formularios Web Forms](https://devblogs.microsoft.com/aspnet/blazor-aspnet-webforms-ebook/). Además, muchos controles de formularios Web Forms se han trasladado a extraordinarias como parte de un proyecto de comunidad de código abierto, [los componentes de Web Forms increíbles](https://fritzandfriends.github.io/BlazorWebFormsComponents/). Con estos componentes, puede trasladar más fácilmente las páginas de formularios Web Forms a increíble, incluso si usan los controles de formularios Web Forms integrados.

## <a name="summary"></a>Resumen

No se admite la migración directa de formularios Web Forms de ASP.NET a ASP.NET Core. Sin embargo, existen estrategias para facilitar el traslado a ASP.NET Core. Puede migrar la funcionalidad de formularios Web Forms para ASP.NET Core correctamente mediante:

* Mantener la funcionalidad no Web fuera de sus proyectos.
* Usar API Web siempre que sea posible.
* Considere la posibilidad de aumentar la cantidad de una interfaz de usuario más moderna.

## <a name="references"></a>Referencias

- [Libro electrónico gratuito: increíbles para desarrolladores de formularios Web Forms de ASP.NET](https://devblogs.microsoft.com/aspnet/blazor-aspnet-webforms-ebook/)
- [Componentes de formularios Web increíbles (proyecto de la comunidad)](https://fritzandfriends.github.io/BlazorWebFormsComponents/)

>[!div class="step-by-step"]
>[Anterior](incremental-migration-strategies.md)
>[Siguiente](deployment-strategies.md)
