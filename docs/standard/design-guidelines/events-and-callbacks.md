---
title: "Eventos y devoluciones de llamada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "eventos [.NET Framework], extensibilidad"
  - "devolución de llamada, de métodos [.NET Framework]"
  - "métodos de devolución de llamada"
  - "devoluciones de llamada"
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Eventos y devoluciones de llamada
Las devoluciones de llamada son los puntos de extensibilidad que permiten un marco para volver a llamar al código de usuario a través de un delegado. Estos delegados se pasan normalmente al marco a través de un parámetro de un método.  
  
 Los eventos son un caso especial de devoluciones de llamada que admite la sintaxis adecuada y coherente para suministrar al delegado \(un controlador de eventos\). Además, la finalización de instrucciones y los diseñadores de Visual Studio proporcionan ayuda sobre el uso de las API basadas en eventos. \(Vea [Diseño de eventos](../../../docs/standard/design-guidelines/event.md).\)  
  
 **✓, considere la posibilidad de** mediante devoluciones de llamada para permitir a los usuarios proporcionar código personalizado para ser ejecutado por el marco de trabajo.  
  
 **✓, considere la posibilidad de** mediante eventos para permitir a los usuarios personalizar el comportamiento de un marco de trabajo sin necesidad de entender el diseño orientado a objetos.  
  
 **✓ hacer** eventos son preferibles las devoluciones de llamada sin formato, porque son mucho más familiares para una gama más amplia de desarrolladores y se integran con la finalización de instrucciones de Visual Studio.  
  
 **Evitar X** usar devoluciones de llamada de API sensibles al rendimiento.  
  
 **✓ hacer** utilizar el nuevo `Func<...>`, `Action<...>`, o `Expression<...>` en lugar de delegados personalizados, al definir las API con devoluciones de llamada.  
  
 `Func<...>` y `Action<...>` representan los delegados genéricos.`Expression<...>` representa las definiciones de función que se pueden compilar y posteriormente se invoca en tiempo de ejecución pero que se puede también se serialicen y se pasa a procesos remotos.  
  
 **✓ hacer** medir y comprender las implicaciones de rendimiento de uso `Expression<...>`, en lugar de utilizar `Func<...>` y `Action<...>` los delegados.  
  
 `Expression<...>` los tipos son generalmente equivalente lógicamente a `Func<...>` y `Action<...>` los delegados. La diferencia principal entre ellos es que los delegados están diseñados para utilizarse en escenarios de proceso local; las expresiones están pensadas para casos sea útil y posibles evaluar la expresión en una máquina o un proceso remoto.  
  
 **✓ hacer** entender que, al llamar a un delegado, se ejecuta código arbitrario y que podría tener repercusiones de seguridad, exactitud y compatibilidad.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)