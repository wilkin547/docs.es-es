---
title: "Dise&#241;ar extensibilidad | Microsoft Docs"
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
  - "extender bibliotecas de clases"
  - "extensibilidad con bibliotecas de clases de .NET Framework"
  - "instrucciones de diseño clases biblioteca [.NET Framework], extensibilidad"
  - "extensibilidad de la biblioteca de clases [.NET Framework]"
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Dise&#241;ar extensibilidad
Un aspecto importante del diseño de un marco es asegurarse de que considera cuidadosamente la extensibilidad del marco. Esto requiere que comprende los costos y beneficios asociados con distintos mecanismos de extensibilidad. Este capítulo le ayuda a decidir cuál de los mecanismos de extensibilidad: subclases, eventos, los miembros virtuales, las devoluciones de llamada y así sucesivamente, puede cumplir mejor los requisitos de su marco.  
  
 Hay muchas maneras de permitir la extensibilidad en marcos. Abarcan desde el menos eficaz pero menos costosa para muy eficaz pero costoso. Para cualquier requisito de extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos. Tenga en cuenta que normalmente es posible agregar más extensibilidad más adelante, pero nunca puede llevarlo lejos sin introducir cambios importantes.  
  
## En esta sección  
 [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Miembros protegidos](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventos y devoluciones de llamada](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstracciones \(tipos e Interfaces abstractos\)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Clases base para implementar abstracciones](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Sellar](../../../docs/standard/design-guidelines/sealing.md)  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)