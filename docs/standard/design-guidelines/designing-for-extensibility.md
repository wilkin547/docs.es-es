---
title: Diseñar extensibilidad
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46508994"
---
# <a name="designing-for-extensibility"></a>Diseñar extensibilidad
Un aspecto importante del diseño de un marco de trabajo es asegurarse de que la extensibilidad del marco se ha considerado atentamente. Esto requiere que comprenda los costos y beneficios asociados con distintos mecanismos de extensibilidad. Este capítulo le ayuda a decidir cuál de los mecanismos de extensibilidad: subclases, eventos, los miembros virtuales, las devoluciones de llamada y así sucesivamente, puede cumplir mejor los requisitos de su marco.  
  
 Hay muchas maneras para permitir la extensibilidad en marcos de trabajo. Abarcan desde el menos eficaz pero menos costosos a muy eficaz pero costoso. Para cualquier requisito extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos. Tenga en cuenta que es normalmente posible agregar más extensibilidad más adelante, pero nunca puede llevarlo lejos sin introducir cambios importantes.  
  
## <a name="in-this-section"></a>En esta sección  
 [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Miembros protegidos](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventos y devoluciones de llamada](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstracciones (Tipos e interfaces abstractos)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Clases base para implementar abstracciones](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Sellado](../../../docs/standard/design-guidelines/sealing.md)  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
