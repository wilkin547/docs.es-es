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
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709418"
---
# <a name="events-and-callbacks"></a>Eventos y devoluciones de llamada
Las devoluciones de llamada son puntos de extensibilidad que permiten a un marco volver a llamar al código de usuario a través de un delegado. Estos delegados se pasan normalmente al marco de trabajo a través de un parámetro de un método.  
  
 Los eventos son un caso especial de devoluciones de llamada que admite una sintaxis adecuada y coherente para proporcionar el delegado (un controlador de eventos). Además, los diseñadores y la finalización de instrucciones de Visual Studio proporcionan ayuda para el uso de API basadas en eventos. (Consulte [diseño de eventos](../../../docs/standard/design-guidelines/event.md)).  
  
 **✓ CONSIDER** usando las devoluciones de llamada que permite a los usuarios proporcionar código personalizado para ser ejecutado por el marco de trabajo.  
  
 **✓ CONSIDER** mediante eventos para permitir a los usuarios personalizar el comportamiento de un marco de trabajo sin necesidad de entender el diseño orientado a objetos.  
  
 **✓ DO** eventos son preferibles las devoluciones de llamada sin formato, porque son mucho más familiares para una gama más amplia de los desarrolladores y se integran con la finalización de instrucciones de Visual Studio.  
  
 **X AVOID** usar devoluciones de llamada de API sensibles al rendimiento.  
  
 **✓ DO** use la nueva `Func<...>`, `Action<...>`, o `Expression<...>` tipos en lugar de delegados personalizados, al definir las API con las devoluciones de llamada.  
  
 `Func<...>` y `Action<...>` representan delegados genéricos. `Expression<...>` representa definiciones de función que se pueden compilar e invocar posteriormente en tiempo de ejecución, pero también se pueden serializar y pasar a procesos remotos.  
  
 **✓ DO** medir y comprender las implicaciones de rendimiento de uso `Expression<...>`, en lugar de usar `Func<...>` y `Action<...>` delegados.  
  
 `Expression<...>` tipos son en la mayoría de los casos lógicamente equivalentes a los delegados de `Func<...>` y `Action<...>`. La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de procesos locales; las expresiones están destinadas a los casos en los que resulta ventajoso y posible evaluar la expresión en un proceso o equipo remoto.  
  
 **✓ DO** entender que mediante una llamada a un delegado, se ejecuta código arbitrario y que podría tener repercusiones de seguridad, la exactitud y compatibilidad.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
