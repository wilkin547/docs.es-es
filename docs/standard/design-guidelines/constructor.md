---
title: Diseño de constructores
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401248"
---
# <a name="constructor-design"></a>Diseño de constructores

Hay dos tipos de constructores: constructores de tipos y constructores de instancia.

Los constructores de tipos son estáticos y los ejecuta CLR antes de usar el tipo. Los constructores de instancias se ejecutan cuando se crea una instancia de un tipo.

Los constructores de tipos no pueden tomar ningún parámetro. Los constructores de instancias pueden. Los constructores de instancias que no toman ningún parámetro a menudo se denominan constructores sin parámetros.

Los constructores son la forma más natural de crear instancias de un tipo. La mayoría de los desarrolladores buscarán e intentarán usar un constructor antes de considerar formas alternativas de crear instancias (como métodos de fábrica).

✔️ CONSIDERA proporcionar constructores simples, idealmente predeterminados.

Un constructor simple tiene un número muy pequeño de parámetros y todos los parámetros son primitivos o enumeraciones. Estos constructores simples aumentan la usabilidad del marco.

✔️ CONSIDERA mediante un método de fábrica estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si seguir las directrices de diseño del constructor se siente antinatural.

✔️ DO usar parámetros de constructor como accesos directos para establecer las propiedades principales.

No debe haber ninguna diferencia en la semántica entre el uso del constructor vacío seguido de algunos conjuntos de propiedades y el uso de un constructor con varios argumentos.

✔️ DO usan el mismo nombre para los parámetros del constructor y una propiedad si los parámetros del constructor se utilizan para establecer simplemente la propiedad.

La única diferencia entre estos parámetros y las propiedades debe ser mayúsculas y minúsculas.

✔️ hacer un trabajo mínimo en el constructor.

Los constructores no deben hacer mucho trabajo que no sea capturar los parámetros del constructor. El costo de cualquier otro procesamiento debe retrasarse hasta que sea necesario.

✔️, no produzca excepciones de los constructores de instancias, si procede.

✔️ DO declara explícitamente el constructor public sin parámetros en las clases, si se requiere dicho constructor.

Si no declara explícitamente ningún constructor en un tipo, muchos lenguajes (por ejemplo, C-) agregarán automáticamente un constructor público sin parámetros. (Las clases abstractas obtienen un constructor protegido.)

Agregar un constructor con parámetros a una clase impide que el compilador agregue el constructor sin parámetros. Esto a menudo provoca cambios accidentales en las roturas.

❌EVITAR la definición explícita de constructores sin parámetros en structs.

Esto hace que la creación de matrices sea más rápida, porque si el constructor sin parámetros no está definido, no tiene que ejecutarse en todas las ranuras de la matriz. Tenga en cuenta que muchos compiladores, incluido el lenguaje c, no permiten que los structs tengan constructores sin parámetros por este motivo.

❌EVITAR llamar a miembros virtuales en un objeto dentro de su constructor.

Llamar a un miembro virtual hará que se llame a la invalidación más derivada, incluso si el constructor del tipo más derivado aún no se ha ejecutado completamente.

## <a name="type-constructor-guidelines"></a>Pautas para constructores de tipos

✔️ HACER que los constructores estáticos sean privados.

Un constructor estático, también denominado constructor de clase, se utiliza para inicializar un tipo. El CLR llama al constructor estático antes de que se cree la primera instancia del tipo o se llame a cualquier miembro estático de ese tipo. El usuario no tiene control sobre cuándo se llama al constructor estático. Si un constructor estático no es privado, se puede llamar mediante código que no sea CLR. Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado. El compilador de C- fuerza los constructores estáticos a ser privados.

❌NO produzca excepciones de constructores estáticos.

Si se produce una excepción desde un constructor de tipos, el tipo no se puede usar en el dominio de aplicación actual.

✔️ CONSIDERAR la inicialización de campos estáticos en línea en lugar de usar explícitamente constructores estáticos, porque el tiempo de ejecución es capaz de optimizar el rendimiento de tipos que no tienen un constructor estático definido explícitamente.

*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
