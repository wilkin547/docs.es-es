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
ms.openlocfilehash: 68419fe293dd25936aa3c1e3def10bbe8852e175
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571389"
---
# <a name="designing-for-extensibility"></a>Diseñar extensibilidad
Un aspecto importante del diseño de un marco de trabajo consiste en asegurarse que la extensibilidad del marco tengan en cuidadosa consideración. Esto requiere que se conozca los costos y beneficios asociados con diversos mecanismos de extensibilidad. Este capítulo le ayudará a decidir cuál de los mecanismos de extensibilidad: subclases, eventos, los miembros virtuales, las devoluciones de llamada y así sucesivamente, pueden satisfacer mejor los requisitos de su marco.  
  
 Hay muchas maneras de permitir la extensibilidad en marcos de trabajo. Abarcan desde menos eficaces pero menos costosa para una acción muy potente pero costoso. Para cualquier requisito de extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos. Tenga en cuenta que normalmente es posible agregar más extensibilidad más tarde, pero nunca puede dejarlo inmediatamente sin introducir cambios importantes.  
  
## <a name="in-this-section"></a>En esta sección  
 [Clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Miembros protegidos](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventos y devoluciones de llamada](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstracciones (Tipos e interfaces abstractos)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Clases base para implementar abstracciones](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Sellado](../../../docs/standard/design-guidelines/sealing.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
