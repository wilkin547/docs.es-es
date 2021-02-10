---
description: 'Más información acerca de: Sellar'
title: Sellar
ms.date: 10/22/2008
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: 94673f793aa7373e1076e13cbda900fba83786f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731726"
---
# <a name="sealing"></a>Sellar

Una de las características de los marcos orientados a objetos es que los desarrolladores pueden ampliarlos y personalizarlos de formas imprevistas para los diseñadores de marcos. Esta es la eficacia y el peligro del diseño extensible. Al diseñar el marco, es, por lo tanto, muy importante diseñar cuidadosamente para la extensibilidad cuando se desee y limitar esta cuando haya peligro.

 Un mecanismo eficaz que evita la extensibilidad es el sellado. Puede sellar los miembros individuales o de clase. Sellar una clase impide que los usuarios hereden de la clase. Sellar un miembro impide que los usuarios invaliden un miembro determinado.

 ❌ NO selle clases sin tener una buena razón para hacerlo.

 Sellar una clase porque no puede pensar en un escenario de extensibilidad no es una buena razón. A los usuarios del marco les gusta heredar de clases por diversas razones no evidentes, como la incorporación de miembros de conveniencia. Consulte [Clases no selladas](unsealed-classes.md) por ver ejemplos de razones no evidentes que los usuarios desean heredar de un tipo.

 Entre las razones buenas para sellar una clase se incluyen las siguientes:

- La clase es una clase estática. Consulte [Diseño de clases estáticas](static-class.md).

- La clase almacena secretos que afectan a la seguridad en miembros protegidos heredados.

- La clase hereda muchos miembros virtuales y el costo de sellarlos individualmente superaría las ventajas de dejar la clase sin sellar.

- La clase es un atributo que requiere una búsqueda de tiempo de ejecución muy rápida. Los atributos sellados tienen niveles de rendimiento ligeramente mayores que los no sellados. Consulte [Atributos](attributes.md).

 ❌ NO declare miembros protegidos ni virtuales en tipos sellados.

 Por definición, los tipos sellados no se pueden heredar de ahí. Esto significa que no se puede llamar a los miembros protegidos en tipos sellados y que tampoco se pueden invalidar los métodos virtuales en tipos sellados.

 ✔️ CONSIDERE la posibilidad de sellar los miembros que invalide.

 Los problemas que pueden surgir de la presentación de miembros virtuales (como se indica en [Miembros virtuales](virtual-members.md)) se aplican también a las invalidaciones, aunque en un grado ligeramente menor. Sellar una invalidación le protege de estos problemas a partir de ese punto en la jerarquía de herencia.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
- [Clases no selladas](unsealed-classes.md)
