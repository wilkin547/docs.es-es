---
title: "Abstracciones (tipos e Interfaces abstractos) | Microsoft Docs"
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
  - "Resumen de interfaces [.NET Framework]"
  - "interfaces abstractas [.NET Framework]"
  - "tipos abstractos [.NET Framework]"
  - "Resumen de tipos [.NET Framework]"
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Abstracciones (tipos e Interfaces abstractos)
Una abstracción es un tipo que describe un contrato, pero no proporciona una implementación completa del contrato. Abstracciones normalmente se implementan como interfaces o clases abstractas y vienen con un conjunto bien definido de documentación de referencia que describe la semántica necesaria de los tipos que implementan el contrato. Algunas de las abstracciones más importantes en .NET Framework son <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, y <xref:System.Object>.  
  
 Puede extender marcos mediante la implementación de un tipo concreto que admite el contrato de una abstracción y usar este tipo concreto con framework API consume \(que opera en\) la abstracción.  
  
 Es muy difícil de diseñar una abstracción lógica y útil que es capaz de soportar la prueba de tiempo. La dificultad principal es obtener el conjunto de miembros, nada más y menos no correcto. Si una abstracción tiene demasiados miembros, resulta difícil o incluso imposible implementar. Si tiene pocos miembros para la funcionalidad prometida, resulta inútil en muchos escenarios interesantes.  
  
 Demasiados abstracciones en un marco de trabajo también afectar negativamente al uso de framework. A menudo resulta bastante difícil de comprender una abstracción sin comprender cómo encaja en la imagen más grande de las implementaciones concretas y las API que operan en la abstracción. Además, los nombres de las abstracciones y sus miembros son necesariamente abstractos, que a menudo es críptico y distante sin entender primero el contexto más amplio de su uso.  
  
 Sin embargo, las abstracciones proporcionan extensibilidad muy eficaz que a menudo no pueden coincidir con los otros mecanismos de extensibilidad. Son el núcleo de muchos patrones de arquitectura, como los complementos, inversión de control \(IoC\), canalizaciones y así sucesivamente. También son muy importantes para efectuar pruebas de marcos. Buena abstracciones permiten pesadas dependencias con el fin de pruebas unitarias de código auxiliar. En resumen, las abstracciones son responsables de la riqueza de los marcos modernas orientada a objetos solicitada.  
  
 **X no** proporcionan abstracciones a menos que estén probadas desarrollando algunas implementaciones concretas y API que consumen las abstracciones.  
  
 **✓ hacer** Elija cuidadosamente entre una clase abstracta y una interfaz al diseñar una abstracción.  
  
 **✓ considere** proporcionar pruebas de referencia para las implementaciones concretas de abstracciones. Tales comprobaciones deberían permitir a los usuarios probar si sus implementaciones cumplen correctamente el contrato.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)