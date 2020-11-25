---
title: Diseñar extensibilidad
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 7b7b1bcfc907612be12e7f8ca7114183f7e830ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734457"
---
# <a name="designing-for-extensibility"></a>Diseñar extensibilidad

Un aspecto importante del diseño de un marco es asegurarse de que se ha tenido cuidado en la extensibilidad del marco de trabajo. Esto requiere que comprenda los costos y beneficios asociados con los distintos mecanismos de extensibilidad. Este capítulo le ayuda a decidir cuál de los mecanismos de extensibilidad (subclases, eventos, miembros virtuales, devoluciones de llamada, etc.) puede satisfacer mejor los requisitos de su marco de trabajo.  
  
 Hay muchas maneras de permitir la extensibilidad en marcos de trabajo. Van desde menos eficaz, pero menos costosas hasta muy eficaces pero costosas. Para cualquier requisito de extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos. Tenga en cuenta que normalmente es posible agregar más extensibilidad más adelante, pero nunca puede quitarla sin introducir cambios importantes.  
  
## <a name="in-this-section"></a>En esta sección  

 [Clases no selladas](unsealed-classes.md)  
 [Miembros protegidos](protected-members.md)  
 [Eventos y devoluciones de llamada](events-and-callbacks.md)  
 [Miembros virtuales](virtual-members.md)  
 [Abstracciones (tipos e interfaces abstractos)](abstractions-abstract-types-and-interfaces.md)  
 [Clases base para implementar abstracciones](base-classes-for-implementing-abstractions.md)  
 [Sellar](sealing.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
