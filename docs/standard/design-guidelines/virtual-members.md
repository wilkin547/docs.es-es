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
ms.openlocfilehash: fa4227fc4476b86f07216650b22fccc25af7dd98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-members"></a>Miembros virtuales
Pueden invalidar los miembros virtuales, lo que cambiar el comportamiento de la subclase. Son muy similares a las devoluciones de llamada en cuanto a la extensibilidad que proporcionan, pero son mejores en cuanto a rendimiento de la ejecución y el consumo de memoria. Además, los miembros virtuales se sienten más naturales en escenarios que requieren la creación una clase especial de tipo de un tipo existente (especialización).  
  
 Los miembros virtuales funcionan mejor que las devoluciones de llamada y eventos, pero no se realizan mejor que los métodos no virtuales.  
  
 El principal inconveniente de los miembros virtuales es que solo se puede modificar el comportamiento de un miembro virtual en el momento de la compilación. El comportamiento de una devolución de llamada puede modificarse en tiempo de ejecución.  
  
 Los miembros virtuales, como las devoluciones de llamada (y quizá algo más que las devoluciones de llamada), son costos diseñar, probar y mantener, ya que cualquier llamada a un miembro virtual puede reemplazarse de manera impredecible y puede ejecutar código arbitrario. Además, mucho más esfuerzo normalmente es necesario definir claramente el contrato de los miembros virtuales, por lo que el costo de diseñar y documentar ellos es mayor.  
  
 **X DO NOT** hacer que los miembros virtuales a menos que tenga una buena razón para hacerlo y tenga en cuenta todos los costes asociados a diseñar, probar y mantener los miembros virtuales.  
  
 Los miembros virtuales son menos tolerante a las modificaciones en cuanto a los cambios que pueden realizarse en ellos sin interrumpir la compatibilidad. Además, son más lentas que los miembros no virtuales, principalmente porque no se alinean las llamadas a los miembros virtuales.  
  
 **✓ Considere la posibilidad de** limitar la extensibilidad para solo lo que sea absolutamente necesario.  
  
 **✓ HACER** preferir accesibilidad protegida accesibilidad pública para los miembros virtuales. Los miembros públicos deberían proporcionar extensibilidad (si es necesario) mediante una llamada a un miembro virtual protegida.  
  
 Los miembros públicos de una clase deben proporcionar el conjunto adecuado de funcionalidad para los consumidores directa de esa clase. Los miembros virtuales están diseñados para invalidarse en subclases y accesibilidad protegida es una excelente manera de definir el ámbito de todos los puntos de extensibilidad virtual a dónde pueden utilizarse.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
