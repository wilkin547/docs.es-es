---
title: Miembros virtuales
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92b648e7886fb0214238e32eacae2870b470340
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892803"
---
# <a name="virtual-members"></a>Miembros virtuales
Pueden invalidar los miembros virtuales, lo que cambiará el comportamiento de la subclase. Son muy similares a las devoluciones de llamada en cuanto a la extensibilidad que proporcionan, pero están mejores en términos de rendimiento de la ejecución y el consumo de memoria. Además, los miembros virtuales resultar más naturales en escenarios que requieren la creación de un especial de un tipo existente (especialización).  
  
 Los miembros virtuales funcionan mejor que las devoluciones de llamada y eventos, pero no lleva a cabo un mejor rendimiento que los métodos no virtuales.  
  
 La principal desventaja de los miembros virtuales es que solo se puede modificar el comportamiento de un miembro virtual en el momento de la compilación. El comportamiento de una devolución de llamada puede modificarse en tiempo de ejecución.  
  
 Los miembros virtuales, como las devoluciones de llamada (y quizá algo más que las devoluciones de llamada), son costosos de diseñar, probar y mantener, ya que cualquier llamada a un miembro virtual puede reemplazarse de manera impredecible y puede ejecutar código arbitrario. Además, mucho más esfuerzo normalmente es necesario definir claramente el contrato de los miembros virtuales, por lo que el costo de diseño y la documentación de ellos es mayor.  
  
 **X DO NOT** hacer que los miembros virtuales a menos que tenga una buena razón para hacerlo y tenga en cuenta todos los costes asociados a diseñar, probar y mantener los miembros virtuales.  
  
 Los miembros virtuales son menos flexible en cuanto a los cambios que se pueden realizar en ellos sin interrumpir la compatibilidad. Además, son más lentos que los miembros que no son virtuales, principalmente porque no se alinean las llamadas a los miembros virtuales.  
  
 **✓ CONSIDER** limitar la extensibilidad para solo lo que sea absolutamente necesario.  
  
 **✓ DO** preferir accesibilidad protegida accesibilidad pública para los miembros virtuales. Los miembros públicos deben proporcionar extensibilidad (si es necesario) mediante una llamada a un miembro virtual protegida.  
  
 Los miembros públicos de una clase deben proporcionar el conjunto correcto de funcionalidad para los consumidores directos de esa clase. Los miembros virtuales están diseñados para invalidarse en subclases y accesibilidad protegida es una excelente manera de definir el ámbito de todos los puntos de extensibilidad virtual donde se pueden usar.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
