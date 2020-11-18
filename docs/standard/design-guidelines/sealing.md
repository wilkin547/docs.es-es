---
title: Sellar
ms.date: 10/22/2008
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: 29023ad431f9d05caf44e59f66eccee24bfa0433
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828691"
---
# <a name="sealing"></a>Sellar
Una de las características de los marcos de trabajo orientados a objetos es que los desarrolladores pueden ampliarlas y personalizarlas de maneras inesperadas por los diseñadores de Marcos. Esta es la eficacia y el peligro del diseño extensible. Al diseñar el marco de trabajo, es, por lo tanto, muy importante diseñar cuidadosamente la extensibilidad para que se desee y limitar la extensibilidad cuando sea peligrosa.

 Un mecanismo eficaz que evita la extensibilidad es el sellado. Puede sellar la clase o los miembros individuales. Sellar una clase impide que los usuarios hereden de la clase. El sellado de un miembro impide que los usuarios invaliden un miembro determinado.

 ❌ No selle clases sin tener una buena razón para hacerlo.

 Sellar una clase porque no se puede pensar en un escenario de extensibilidad no es una buena razón. Los usuarios del marco de trabajo como para heredar de clases por diversos motivos no obvios, como agregar miembros de conveniencia. Consulte [clases no selladas](unsealed-classes.md) para obtener ejemplos de razones no obvias que los usuarios desean heredar de un tipo.

 Los motivos buenos para sellar una clase son los siguientes:

- La clase es una clase estática. Vea [diseño de clases estáticas](static-class.md).

- La clase almacena secretos confidenciales de seguridad en miembros protegidos heredados.

- La clase hereda muchos miembros virtuales y el costo de sellarlas individualmente superaría las ventajas de mantener la clase sin sellar.

- La clase es un atributo que requiere una búsqueda muy rápida en tiempo de ejecución. Los atributos sellados tienen niveles de rendimiento ligeramente mayores que los no sellados. Vea [atributos](attributes.md).

 ❌ NO declare miembros protegidos o virtuales en tipos sellados.

 Por definición, los tipos sellados no se pueden heredar de. Esto significa que no se puede llamar a los miembros protegidos en tipos sellados y no se pueden invalidar los métodos virtuales en tipos sellados.

 ✔️ considere la posibilidad de sellar los miembros que invalide.

 Los problemas que pueden derivarse de la introducción de miembros virtuales (descritos en [miembros virtuales](virtual-members.md)) también se aplican a las invalidaciones, aunque a un grado ligeramente inferior. Sellar una invalidación le protege de estos problemas a partir de ese punto en la jerarquía de herencia.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño de marco](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
- [Clases no selladas](unsealed-classes.md)
