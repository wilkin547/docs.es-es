---
description: 'Más información acerca de: Eventos y devoluciones de llamada'
title: Eventos y devoluciones de llamada
ms.date: 10/22/2008
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 8a9049808ec0f7a490889ab1f17c4d8b8e8bd2b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642154"
---
# <a name="events-and-callbacks"></a>Eventos y devoluciones de llamada

Las devoluciones de llamada son puntos de extensibilidad que permiten a un marco volver a llamar al código de usuario a través de un delegado. Estos delegados se pasan normalmente al marco a través de un parámetro de un método.

 Los eventos son un caso especial de devoluciones de llamada que admiten una sintaxis adecuada y coherente para proporcionar el delegado (un controlador de eventos). Además, los diseñadores y la finalización de instrucciones de Visual Studio proporcionan ayuda para utilizar las API basadas en eventos. (Consulte [Diseño de eventos](event.md)).

 ✔️ PLANTÉESE la posibilidad de usar devoluciones de llamada para permitir que los usuarios proporcionen código personalizado para que lo ejecute el marco.

 ✔️ PLANTÉESE la posibilidad de usar eventos para que los usuarios puedan personalizar el comportamiento de un marco sin necesidad de entender el diseño orientado a objetos.

 ✔️ OPTE por eventos en lugar de devoluciones de llamada sin formato, porque son más familiares para una gama más amplia de desarrolladores y están integrados con la finalización de declaraciones de Visual Studio.

 ❌ EVITE usar devoluciones de llamada en las API sensibles al rendimiento.

 ✔️ DEBE usar los nuevos tipos de `Func<...>`, `Action<...>` o `Expression<...>` en lugar de los delegados personalizados al definir las API con devoluciones de llamada.

 `Func<...>` y `Action<...>` representan delegados genéricos. `Expression<...>` representa definiciones de función que se pueden compilar e invocar posteriormente en tiempo de ejecución, pero también se pueden serializar y pasar a procesos remotos.

 ✔️ DEBE medir y comprender las implicaciones de rendimiento que supone usar `Expression<...>`, en lugar de usar los delegados `Func<...>` y `Action<...>`.

 En la mayoría de los casos, los tipos `Expression<...>` son lógicamente equivalentes a los delegados `Func<...>` y `Action<...>`. La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de procesos locales; las expresiones están indicadas para los casos en los que resulta ventajoso y posible evaluar la expresión en un proceso o equipo remoto.

 ✔️ DEBE comprender que, al llamar a un delegado, está ejecutando código arbitrario y que podría tener repercusiones en la seguridad, la exactitud y la compatibilidad.

 *Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Diseñar extensibilidad](designing-for-extensibility.md)
- [Instrucciones de diseño de .NET Framework](index.md)
