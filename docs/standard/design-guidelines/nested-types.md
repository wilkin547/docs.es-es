---
description: 'Más información acerca de: Tipos anidados'
title: Tipos anidados
ms.date: 10/22/2008
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: 07d81827d67e50351f442ec15ca6cb18a63160fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713382"
---
# <a name="nested-types"></a>Tipos anidados

Un tipo anidado es un tipo definido dentro del ámbito de otro tipo, que se denomina tipo envolvente. Un tipo anidado tiene acceso a todos los miembros de su tipo envolvente. Por ejemplo, tiene acceso a los campos privados definidos en el tipo envolvente y a los campos protegidos definidos en todos los antecesores del tipo envolvente.

 En general, los tipos anidados deben usarse con moderación. Hay varias razones para ello. Algunos desarrolladores no están totalmente familiarizados con el concepto. Por ejemplo, estos desarrolladores podrían tener problemas con la sintaxis de declarar variables de tipos anidados. Los tipos anidados también están estrechamente unidos a sus tipos envolventes y, como tales, no son adecuados para ser tipos de uso general.

 Los tipos anidados son especialmente apropiados para modelar los detalles de implementación de sus tipos envolventes. El usuario final raramente debe tener que declarar variables de un tipo anidado y casi nunca debería tener que crear explícitamente instancias de tipos anidados. Por ejemplo, el enumerador de una colección puede ser un tipo anidado de esa colección. Normalmente se crean instancias de los enumeradores por su tipo envolvente y, dado que muchos lenguajes admiten la instrucción foreach, las variables de enumerador rara vez deben declararse por el usuario final.

 ✔️ USE tipos anidados cuando la relación entre el tipo anidado y su tipo externo sea tal que la semántica de accesibilidad de miembros sea deseable.

 ❌ NO use tipos anidados públicos como una construcción de agrupación lógica; use espacios de nombres para esto.

 ❌ EVITE los tipos anidados expuestos públicamente. La única excepción a esto es si las variables del tipo anidado deben declararse solo en escenarios poco frecuentes, como la creación de subclases u otros escenarios de personalización avanzados.

 ❌ NO use tipos anidados si es probable que se haga referencia al tipo fuera del tipo contenedor.

 Por ejemplo, una enumeración que se pasa a un método definido en una clase no debe definirse como un tipo anidado en la clase.

 ❌ NO use tipos anidados si es necesario crear instancias de estos por código de cliente.  Si un tipo tiene un constructor público, probablemente no se deba anidar.

 Si se pueden crear instancias de un tipo, esto parece indicar que el tipo tiene un lugar en el marco por su cuenta (puede crearlo, trabajar con él y destruirlo sin tener que usar el tipo externo) y, por tanto, no debe anidarse. Los tipos internos no se deben reutilizar ampliamente fuera del tipo externo sin ninguna relación en absoluto con el tipo externo.

 ❌ NO defina un tipo anidado como miembro de una interfaz. Muchos lenguajes no admiten este tipo de construcción.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](type.md)
- [Instrucciones de diseño de .NET Framework](index.md)
