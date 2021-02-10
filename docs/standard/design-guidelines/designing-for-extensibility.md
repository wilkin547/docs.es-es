---
description: 'Más información acerca de: Diseñar extensibilidad'
title: Diseñar extensibilidad
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 148ae25380698a5a1161fb9fbdd3cc60102e865d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642271"
---
# <a name="designing-for-extensibility"></a>Diseñar extensibilidad

Un aspecto importante del diseño de un marco es asegurarse de que se ha considerado detenidamente la extensibilidad del marco. Esto requiere que conozca los costos y las ventajas asociados a los diversos mecanismos de extensibilidad. En este capítulo se le ayuda a decidir cuál de los mecanismos de extensibilidad (creación de subclases, eventos, miembros virtuales, devoluciones de llamada, etc.) puede cumplir mejor los requisitos de su marco.  
  
 Hay muchas maneras de permitir la extensibilidad en marcos. Oscilan entre menos eficaces, pero menos costosas, y muy eficaces, pero costosas. Para cualquier requisito de extensibilidad especificado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos. Tenga en cuenta que normalmente es posible agregar más extensibilidad más adelante, pero nunca puede quitarla sin realizar cambios importantes.  
  
## <a name="in-this-section"></a>En esta sección  

 [Clases no selladas](unsealed-classes.md)  
 [Miembros protegidos](protected-members.md)  
 [Eventos y devoluciones de llamada](events-and-callbacks.md)  
 [Miembros virtuales](virtual-members.md)  
 [Abstracciones (Tipos e interfaces abstractos)](abstractions-abstract-types-and-interfaces.md)  
 [Clases base para implementar abstracciones](base-classes-for-implementing-abstractions.md)  
 [Sellar](sealing.md)  
 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
