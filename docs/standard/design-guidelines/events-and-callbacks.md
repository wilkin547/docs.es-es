---
title: Eventos y devoluciones de llamada
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a6851d1be543fe356827cad67b28cafdc9e56c2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="events-and-callbacks"></a>Eventos y devoluciones de llamada
Las devoluciones de llamada son los puntos de extensibilidad que permiten a un marco de trabajo para volver a llamar al código de usuario a través de un delegado. Estos delegados se pasan normalmente en el marco de trabajo a través de un parámetro de un método.  
  
 Los eventos son un caso especial de devoluciones de llamada que admite la sintaxis adecuada y coherente para suministrar al delegado (un controlador de eventos). Además, la finalización de instrucciones y los diseñadores de Visual Studio proporcionan ayuda sobre el uso de API basadas en eventos. (Consulte [evento diseño](../../../docs/standard/design-guidelines/event.md).)  
  
 **Considere la posibilidad de ✓** usando las devoluciones de llamada que permite a los usuarios proporcionar código personalizado para ser ejecutado por el marco de trabajo.  
  
 **✓ Considere la posibilidad de** mediante eventos para permitir a los usuarios personalizar el comportamiento de un marco de trabajo sin necesidad de entender el diseño orientado a objetos.  
  
 **✓ HACER** eventos son preferibles las devoluciones de llamada sin formato, porque son mucho más familiares para una gama más amplia de los desarrolladores y se integran con la finalización de instrucciones de Visual Studio.  
  
 **X evitar** usar devoluciones de llamada de API sensibles al rendimiento.  
  
 **✓ HACER** use la nueva `Func<...>`, `Action<...>`, o `Expression<...>` tipos en lugar de delegados personalizados, al definir las API con las devoluciones de llamada.  
  
 `Func<...>` y `Action<...>` representan los delegados genéricos. `Expression<...>` representa las definiciones de función que se pueden compilar y posteriormente se invoca en tiempo de ejecución pero también puedan serializar y pasar a un proceso remoto.  
  
 **✓ HACER** medir y comprender las implicaciones de rendimiento de uso `Expression<...>`, en lugar de usar `Func<...>` y `Action<...>` delegados.  
  
 `Expression<...>` tipos están en la mayoría de los casos lógicamente equivalente a `Func<...>` y `Action<...>` delegados. La diferencia principal entre ellas es que los delegados están diseñados para usarse en escenarios de proceso local; expresiones están diseñadas para los casos donde resulta beneficioso y posibles evaluar la expresión en una máquina o un proceso remoto.  
  
 **✓ HACER** entender que mediante una llamada a un delegado, se ejecuta código arbitrario y que podría tener repercusiones de seguridad, la exactitud y compatibilidad.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
