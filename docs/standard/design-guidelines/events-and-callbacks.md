---
title: Eventos y devoluciones de llamada
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 7dab759ba48104530fc41e46f6f2bba18d6c4456
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741655"
---
# <a name="events-and-callbacks"></a>Eventos y devoluciones de llamada
Las devoluciones de llamada son puntos de extensibilidad que permiten a un marco volver a llamar al código de usuario a través de un delegado. Estos delegados se pasan normalmente al marco de trabajo a través de un parámetro de un método.

 Los eventos son un caso especial de devoluciones de llamada que admite una sintaxis adecuada y coherente para proporcionar el delegado (un controlador de eventos). Además, los diseñadores y la finalización de instrucciones de Visual Studio proporcionan ayuda para el uso de API basadas en eventos. (Consulte [diseño de eventos](../../../docs/standard/design-guidelines/event.md)).

 ✔️ considere la posibilidad de usar devoluciones de llamada para permitir que los usuarios proporcionen código personalizado para que lo ejecute el marco de trabajo.

 ✔️ considere la posibilidad de usar eventos para que los usuarios puedan personalizar el comportamiento de un marco sin necesidad de entender el diseño orientado a objetos.

 ✔️ prefieren eventos en lugar de devoluciones de llamada sin formato, ya que están más familiarizados con una amplia gama de desarrolladores y se integran con la finalización de instrucciones de Visual Studio.

 ❌ evitar el uso de devoluciones de llamada en las API sensibles al rendimiento.

 ✔️ usar los nuevos tipos de `Func<...>`, `Action<...>`o `Expression<...>` en lugar de los delegados personalizados, al definir las API con devoluciones de llamada.

 `Func<...>` y `Action<...>` representan delegados genéricos. `Expression<...>` representa definiciones de función que se pueden compilar e invocar posteriormente en tiempo de ejecución, pero también se pueden serializar y pasar a procesos remotos.

 ✔️ medir y comprender las implicaciones de rendimiento del uso de `Expression<...>`, en lugar de usar delegados `Func<...>` y `Action<...>`.

 `Expression<...>` tipos son en la mayoría de los casos lógicamente equivalentes a los delegados de `Func<...>` y `Action<...>`. La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de procesos locales; las expresiones están destinadas a los casos en los que resulta ventajoso y posible evaluar la expresión en un proceso o equipo remoto.

 ✔️ comprender que, al llamar a un delegado, está ejecutando código arbitrario y que podría tener repercusiones en la seguridad, la corrección y la compatibilidad.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
