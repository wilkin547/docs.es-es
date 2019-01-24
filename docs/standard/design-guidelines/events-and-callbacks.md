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
author: KrzysztofCwalina
ms.openlocfilehash: 3609d6ac4847cb081740fd698869df4976f83f8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525487"
---
# <a name="events-and-callbacks"></a>Eventos y devoluciones de llamada
Las devoluciones de llamada son puntos de extensibilidad que permiten un marco de trabajo para volver a llamar al código de usuario a través de un delegado. Estos delegados se pasan normalmente en el marco de trabajo a través de un parámetro de un método.  
  
 Los eventos son un caso especial de devoluciones de llamada que admite la sintaxis adecuada y coherente para suministrar al delegado (un controlador de eventos). Además, la finalización de instrucciones y los diseñadores de Visual Studio proporcionan ayuda sobre cómo usar las API basadas en eventos. (Consulte [diseño eventos](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ CONSIDER** usando las devoluciones de llamada que permite a los usuarios proporcionar código personalizado para ser ejecutado por el marco de trabajo.  
  
 **✓ CONSIDER** mediante eventos para permitir a los usuarios personalizar el comportamiento de un marco de trabajo sin necesidad de entender el diseño orientado a objetos.  
  
 **✓ DO** eventos son preferibles las devoluciones de llamada sin formato, porque son mucho más familiares para una gama más amplia de los desarrolladores y se integran con la finalización de instrucciones de Visual Studio.  
  
 **X AVOID** usar devoluciones de llamada de API sensibles al rendimiento.  
  
 **✓ DO** use la nueva `Func<...>`, `Action<...>`, o `Expression<...>` tipos en lugar de delegados personalizados, al definir las API con las devoluciones de llamada.  
  
 `Func<...>` y `Action<...>` representan los delegados genéricos. `Expression<...>` representa las definiciones de función que se pueden compilar y posteriormente se invoca en tiempo de ejecución, pero puede también serializarse y pasarse a procesos remotos.  
  
 **✓ DO** medir y comprender las implicaciones de rendimiento de uso `Expression<...>`, en lugar de usar `Func<...>` y `Action<...>` delegados.  
  
 `Expression<...>` tipos están en la mayoría de los casos lógicamente equivalente a `Func<...>` y `Action<...>` delegados. La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de proceso local; las expresiones están pensadas para casos donde resulta beneficioso y posibles evaluar la expresión en una máquina o un proceso remoto.  
  
 **✓ DO** entender que mediante una llamada a un delegado, se ejecuta código arbitrario y que podría tener repercusiones de seguridad, la exactitud y compatibilidad.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
