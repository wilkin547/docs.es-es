---
title: Abstracciones (Tipos e interfaces abstractos)
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: KrzysztofCwalina
ms.openlocfilehash: fcf566c24677630fdbb1fcd0eb7628f830b3be2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789225"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstracciones (Tipos e interfaces abstractos)
Una abstracción es un tipo que describe un contrato, pero no proporciona una implementación completa del contrato. Abstracciones normalmente se implementan como interfaces o clases abstractas y vienen con un conjunto de documentación de referencia que describe la semántica necesaria de los tipos que implementan el contrato bien definido. Algunas de las abstracciones más importantes en .NET Framework incluyen <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, y <xref:System.Object>.  
  
 Puede extender marcos de trabajo mediante la implementación de un tipo concreto que admite el contrato de una abstracción y uso de este tipo concreto con framework API consumo (trabajando) la abstracción.  
  
 Es muy difícil de diseñar una abstracción lógica y útil que es capaz de soportar la prueba de tiempo. La dificultad principal es obtener el conjunto de miembros, nada más y menos no correcto. Si una abstracción tiene demasiados miembros, resulta difícil o incluso imposible implementar. Si tiene demasiado pocos miembros para la funcionalidad prometida, resulta inútil en muchos escenarios interesantes.  
  
 Demasiados abstracciones en un marco de trabajo también afectar negativamente a la facilidad de uso de framework. A menudo es bastante difícil entender una abstracción sin entender cómo encaja en la imagen más grande de las implementaciones concretas y las API que operan en la abstracción. Además, los nombres de las abstracciones y sus miembros son necesariamente abstractos, que a menudo es críptico y distante sin entender primero el contexto más amplio de su uso.  
  
 Sin embargo, las abstracciones proporcionan extensibilidad muy eficaz que a menudo no pueden coincidir con los otros mecanismos de extensibilidad. Son el núcleo de muchos modelos arquitectónicos, como los complementos, inversión de control (IoC), canalizaciones y así sucesivamente. También son muy importantes para la capacidad de prueba de marcos de trabajo. Abstracciones buena permiten dependencias pesadas con el fin de las pruebas unitarias de código auxiliar. En resumen, las abstracciones son responsables de la riqueza de los marcos de trabajo modernas orientada a objetos solicitada.  
  
 **X DO NOT** proporcionan abstracciones a menos que se prueban mediante el desarrollo de varias implementaciones concretas y consumir las abstracciones de API.  
  
 **✓ DO** Elija cuidadosamente entre una clase abstracta y una interfaz al diseñar una abstracción.  
  
 **✓ CONSIDER** proporcionar pruebas de referencia para implementaciones concretas de abstracciones. Estas pruebas deben permitir a los usuarios comprobar si sus implementaciones de implementan correctamente el contrato.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
