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
ms.openlocfilehash: 6a4f511af72aad916d367153090504e2a8e11cb8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741817"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstracciones (Tipos e interfaces abstractos)
Una abstracción es un tipo que describe un contrato pero no proporciona una implementación completa del contrato. Las abstracciones se suelen implementar como clases abstractas o interfaces, y incluyen un conjunto bien definido de documentación de referencia que describe la semántica necesaria de los tipos que implementan el contrato. Entre las abstracciones más importantes del .NET Framework se incluyen <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>y <xref:System.Object>.

 Puede extender los marcos implementando un tipo concreto que admita el contrato de una abstracción y usando este tipo concreto con las API de marco de trabajo que consumen (funcionando en) la abstracción.

 Una abstracción significativa y útil que es capaz de resistir la prueba de tiempo es muy difícil de diseñar. La principal dificultad es obtener el conjunto correcto de miembros, ni más ni menos. Si una abstracción tiene demasiados miembros, resulta difícil o incluso imposible de implementar. Si no tiene suficientes miembros para la funcionalidad prometida, se vuelve inútil en muchos escenarios interesantes.

 Demasiadas abstracciones en un marco de trabajo también afectan negativamente a la facilidad de uso del marco de trabajo. A menudo es bastante difícil comprender una abstracción sin comprender cómo encaja en la imagen más grande de las implementaciones concretas y las API que operan en la abstracción. Además, los nombres de las abstracciones y sus miembros son necesariamente abstractos, lo que a menudo hace que sean crípticos e inalcanzables sin tener que entender primero el contexto más amplio de su uso.

 Sin embargo, las abstracciones proporcionan extensibilidad extremadamente eficaz que los demás mecanismos de extensibilidad no suelen coincidir. Son el núcleo de muchos patrones arquitectónicos, como complementos, inversión de control (IoC), canalizaciones, etc. También son muy importantes para la prueba de los marcos de trabajo. Las buenas abstracciones permiten el código auxiliar de las dependencias pesadas con el fin de realizar pruebas unitarias. En Resumen, las abstracciones son responsables de la riqueza buscada de los marcos de trabajo orientados a objetos modernos.

 ❌ no proporcionan abstracciones a menos que se prueben mediante el desarrollo de varias implementaciones concretas y API que consuman las abstracciones.

 ✔️ Elija cuidadosamente entre una clase abstracta y una interfaz al diseñar una abstracción.

 ✔️ considere la posibilidad de proporcionar pruebas de referencia para implementaciones concretas de abstracciones. Dichas pruebas deben permitir que los usuarios prueben si sus implementaciones implementan correctamente el contrato.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
