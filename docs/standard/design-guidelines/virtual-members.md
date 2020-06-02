---
title: Miembros virtuales
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 9eb6cbef969e51dee1a72d402c124d06f08fe5c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288503"
---
# <a name="virtual-members"></a>Miembros virtuales
Los miembros virtuales se pueden invalidar, lo que cambia el comportamiento de la subclase. Son bastante similares a las devoluciones de llamada en términos de extensibilidad que proporcionan, pero son mejores en cuanto al rendimiento de la ejecución y el consumo de memoria. Además, los miembros virtuales se sienten más naturales en escenarios que requieren la creación de una clase especial de un tipo existente (especialización).

 Los miembros virtuales funcionan mejor que las devoluciones de llamada y los eventos, pero no funcionan mejor que los métodos no virtuales.

 El principal inconveniente de los miembros virtuales es que el comportamiento de un miembro virtual solo se puede modificar en el momento de la compilación. El comportamiento de una devolución de llamada se puede modificar en tiempo de ejecución.

 Los miembros virtuales, como las devoluciones de llamada (y quizás más que las devoluciones de llamada), son caros de diseñar, probar y mantener, ya que cualquier llamada a un miembro virtual se puede invalidar de maneras imprevisibles y puede ejecutar código arbitrario. Además, normalmente se requiere mucho más esfuerzo para definir claramente el contrato de los miembros virtuales, por lo que el costo de diseñar y documentarlos es mayor.

 ❌NO haga que los miembros sean virtuales a menos que tenga una buena razón para hacerlo y conozca todos los costos relacionados con el diseño, la prueba y el mantenimiento de los miembros virtuales.

 Los miembros virtuales son menos permisivo en lo que se refiere a los cambios que se pueden realizar en ellos sin interrumpir la compatibilidad. Además, son más lentos que los miembros no virtuales, principalmente porque las llamadas a miembros virtuales no se insertan.

 ✔️ considere la posibilidad de limitar la extensibilidad solo a lo que es absolutamente necesario.

 ✔️ preferir accesibilidad protegida a través de la accesibilidad pública para los miembros virtuales. Los miembros públicos deben proporcionar extensibilidad (si es necesario) llamando a un miembro virtual protegido.

 Los miembros públicos de una clase deben proporcionar el conjunto adecuado de funcionalidad para los consumidores directos de esa clase. Los miembros virtuales están diseñados para invalidarse en las subclases y la accesibilidad protegida es una excelente manera de definir el ámbito de todos los puntos de extensibilidad virtual en donde se pueden usar.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
