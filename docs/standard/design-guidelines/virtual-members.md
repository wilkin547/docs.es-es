---
title: "Miembros virtuales | Microsoft Docs"
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
  - "miembros reemplazables"
  - "miembros virtuales"
  - "miembros [.NET Framework], virtuales"
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Miembros virtuales
Pueden invalidar los miembros virtuales, lo que cambiará el comportamiento de la subclase. Son muy similares a las devoluciones de llamada en cuanto a la extensibilidad que proporcionan, pero están mejores en términos de rendimiento de la ejecución y el consumo de memoria. Además, los miembros virtuales sentirse más naturales en escenarios que requieren la creación de una relación especial de un tipo existente \(especialización\).  
  
 Los miembros virtuales funcionan mejor que las devoluciones de llamada y eventos, pero no se realizan mejor que los métodos no virtuales.  
  
 La principal desventaja de los miembros virtuales es que el comportamiento de un miembro virtual sólo puede modificarse en tiempo de compilación. El comportamiento de devolución de llamada se puede modificar en tiempo de ejecución.  
  
 Los miembros virtuales, como las devoluciones de llamada \(y quizá algo más que las devoluciones de llamada\), son costosos de diseñar, probar y mantener, ya que cualquier llamada a un miembro virtual puede reemplazarse de manera impredecible y puede ejecutar código arbitrario. Además, mucho más esfuerzo normalmente es necesario definir claramente el contrato de los miembros virtuales, por lo que el costo de diseño y documentación es mayor.  
  
 **X no** hacer que los miembros virtuales a menos que tenga una buena razón para hacerlo y está al corriente de todos los costos relacionados con el diseño, pruebas y mantenimiento de miembros virtuales.  
  
 Los miembros virtuales son menos tolerante en cuanto a los cambios que se pueden realizar en ellos sin interrumpir la compatibilidad. Además, son más lentos que los miembros no virtual, principalmente porque las llamadas a miembros virtuales no se escriben.  
  
 **✓ considere** limitar la extensibilidad a sólo lo absolutamente necesario.  
  
 **✓ hacer** preferir accesibilidad protegida accesibilidad pública para los miembros virtuales. Los miembros públicos deberían proporcionar extensibilidad \(si es necesario\) mediante una llamada a un miembro virtual protegido.  
  
 Los miembros públicos de una clase deben proporcionar el conjunto adecuado de funcionalidad para los consumidores directos de esa clase. Los miembros virtuales están diseñados para invalidarse en subclases y accesibilidad protegida es una excelente manera de definir el ámbito de todos los puntos de extensibilidad virtual donde se pueden usar.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)