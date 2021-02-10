---
description: 'Más información acerca de: Abstracciones (Tipos e interfaces abstractos)'
title: Abstracciones (Tipos e interfaces abstractos)
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
ms.openlocfilehash: 8dc82f004d655429e842c63fab4defff0fd74ab2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642447"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstracciones (Tipos e interfaces abstractos)

Una abstracción es un tipo que describe un contrato, pero no proporciona una implementación completa del contrato. Las abstracciones se suelen implementar como clases abstractas o interfaces, e incluyen un conjunto bien definido de documentación de referencia que describe la semántica necesaria de los tipos que implementan el contrato. Entre las abstracciones más importantes de .NET Framework se encuentran <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.Object>.

 Puede extender los marcos implementando un tipo concreto que admita el contrato de una abstracción y usando este tipo concreto con las API del marco que consumen la abstracción u operan en ella.

 Una abstracción significativa y útil que pueda resistir la prueba del tiempo es muy difícil de diseñar. La principal dificultad es obtener el conjunto correcto de miembros, ni más ni menos. Si una abstracción tiene demasiados miembros, será difícil o incluso imposible de implementar. Si no tiene suficientes miembros para la funcionalidad prometida, será inservible en muchos escenarios interesantes.

 Si un marco tiene demasiadas abstracciones, también afecta negativamente a la facilidad de uso de dicho marco. A menudo es bastante difícil entender una abstracción sin comprender cómo encaja en el panorama más amplio de las implementaciones concretas y las API que operan en la abstracción. Además, los nombres de las abstracciones y sus miembros son necesariamente abstractos, lo que a menudo hace que sean crípticos e inalcanzables sin entender primero el contexto más amplio de su uso.

 Sin embargo, las abstracciones proporcionan una extensibilidad extremadamente eficaz que los demás mecanismos de extensibilidad no suelen igualar. Son el núcleo de muchos patrones arquitectónicos, como complementos, inversión de control (IoC), canalizaciones, etc. También son muy importantes para probar los marcos. Las buenas abstracciones permiten eliminar las dependencias pesadas con el fin de realizar pruebas unitarias. En resumen, las abstracciones son las responsables de la buscada importancia de los marcos modernos orientados a objetos.

 ❌ NO proporcione abstracciones, a menos que se prueben mediante el desarrollo de varias implementaciones concretas y API que consuman las abstracciones.

 ✔️ Elija cuidadosamente entre una clase abstracta y una interfaz al diseñar una abstracción.

 ✔️ Recomendamos proporcionar pruebas de referencia para implementaciones concretas de abstracciones. Dichas pruebas deben permitir que los usuarios prueben si sus implementaciones implementan correctamente el contrato.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
