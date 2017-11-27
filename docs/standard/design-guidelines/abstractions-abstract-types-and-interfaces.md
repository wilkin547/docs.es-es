---
title: Abstracciones (Tipos e interfaces abstractos)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d601ab89b08dd9e9bd0b27d2cfb1c495c33a2786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstracciones (Tipos e interfaces abstractos)
Una abstracción es un tipo que describe un contrato, pero no proporciona una implementación completa del contrato. Abstracciones normalmente se implementan como interfaces o clases abstractas y vienen con un conjunto de documentación de referencia que describe la semántica necesaria de los tipos que implementan el contrato bien definido. Algunas de las abstracciones más importantes en .NET Framework son <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, y <xref:System.Object>.  
  
 Puede ampliar los marcos de trabajo mediante la implementación de un tipo concreto que admita el contrato de una abstracción y usar este tipo concreto con framework API consumo (que opera en) la abstracción.  
  
 Es muy difícil de diseñar una abstracción lógica y útil que es capaz de soportar la prueba de tiempo. La dificultad principal es obtener el conjunto de miembros, nada más y menos no correcto. Si una abstracción tiene demasiados miembros, resulta difícil o imposible implementar. Si tiene demasiado pocos miembros para la funcionalidad prometido, resulta inútil en muchos escenarios interesantes.  
  
 Hay demasiados abstracciones en un marco de trabajo también afectar negativamente al facilidad de uso de framework. A menudo resulta muy difícil de comprender una abstracción sin conocer cómo encaja en la imagen más grande de la API de la abstracción y las implementaciones concretas. Además, los nombres de extracciones y sus miembros son necesariamente abstractos, que a menudo hace que sean crípticos y distante sin conocer primero el contexto más amplio de su uso.  
  
 Sin embargo, abstracciones proporcionan extensibilidad muy eficaz que a menudo no pueden coincidir con los otros mecanismos de extensibilidad. Únicamente son el núcleo de muchos patrones de arquitectura, como complementos, inversión de control (IoC), canalizaciones y así sucesivamente. También son muy importantes para poder realizar pruebas de marcos de trabajo. Buena abstracciones permiten pesadas dependencias con el fin de pruebas unitarias de código auxiliar. En resumen, las abstracciones son responsables de la riqueza de los marcos modernas orientada a objetos solicitada.  
  
 **X DO NOT** proporcionan abstracciones a menos que se prueban mediante el desarrollo de varias implementaciones concretas y consumir las abstracciones de API.  
  
 **✓ HACER** Elija cuidadosamente entre una clase abstracta y una interfaz al diseñar una abstracción.  
  
 **✓ Considere la posibilidad de** proporcionar pruebas de referencia para implementaciones concretas de abstracciones. Dichas pruebas deben permitir a los usuarios comprobar si sus implementaciones cumplen correctamente el contrato.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseñar para la extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
