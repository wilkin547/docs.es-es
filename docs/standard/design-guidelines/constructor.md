---
title: Diseño de constructores
ms.date: 10/22/2008
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
ms.openlocfilehash: 27fb73aa01adf31117d1b82724873db3a03fd269
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821403"
---
# <a name="constructor-design"></a>Diseño de constructores

Hay dos tipos de constructores: constructores de tipo y constructores de instancia.

Los constructores de tipo son estáticos y los ejecuta CLR antes de que se use el tipo. Los constructores de instancia se ejecutan cuando se crea una instancia de un tipo.

Los constructores de tipo no pueden tomar ningún parámetro. Los constructores de instancias pueden. Los constructores de instancias que no toman ningún parámetro se denominan a menudo constructores sin parámetros.

Los constructores son la manera más natural de crear instancias de un tipo. La mayoría de los desarrolladores buscarán e intentarán usar un constructor antes de considerar formas alternativas de crear instancias (como métodos de generador).

✔️ considere la posibilidad de proporcionar constructores simples, idealesmente predeterminados.

Un constructor simple tiene un número muy pequeño de parámetros, y todos los parámetros son primitivos o enumeraciones. Estos constructores simples aumentan la facilidad de uso del marco de trabajo.

✔️ considere la posibilidad de usar un Factory Method estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si las instrucciones de diseño del constructor no son naturales.

✔️ usar parámetros de constructor como métodos abreviados para establecer las propiedades principales.

No debe haber ninguna diferencia en la semántica entre el uso del constructor vacío seguido de algunos conjuntos de propiedades y el uso de un constructor con varios argumentos.

✔️ usar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros de constructor se utilizan para establecer simplemente la propiedad.

La única diferencia entre estos parámetros y las propiedades debe ser la grafía.

✔️ REALIZAR un trabajo mínimo en el constructor.

Los constructores no deben hacer mucho trabajo aparte de capturar los parámetros del constructor. El costo de cualquier otro procesamiento debe retrasarse hasta que sea necesario.

✔️ inician excepciones desde constructores de instancia, si es necesario.

✔️ declaran explícitamente el constructor sin parámetros público en las clases, si se requiere este tipo de constructor.

Si no declara explícitamente ningún constructor en un tipo, muchos lenguajes (como C#) agregarán automáticamente un constructor sin parámetros público. (Las clases abstractas obtienen un constructor protegido).

Agregar un constructor con parámetros a una clase impide que el compilador agregue el constructor sin parámetros. Esto suele provocar cambios bruscos accidentales.

❌ Evite definir explícitamente constructores sin parámetros en Structs.

Esto hace que la creación de matrices sea más rápida, ya que si no se define el constructor sin parámetros, no es necesario que se ejecute en cada ranura de la matriz. Tenga en cuenta que muchos compiladores, incluido C#, no permiten que los Structs tengan constructores sin parámetros por esta razón.

❌ Evite llamar a miembros virtuales en un objeto dentro de su constructor.

La llamada a un miembro virtual hará que se llame a la invalidación más derivada, incluso si el constructor del tipo más derivado aún no se ha ejecutado completamente.

## <a name="type-constructor-guidelines"></a>Instrucciones del constructor de tipos

✔️ hacer que los constructores estáticos sean privados.

Un constructor estático, también denominado constructor de clase, se usa para inicializar un tipo. CLR llama al constructor estático antes de que se cree la primera instancia del tipo o se llame a cualquier miembro estático de ese tipo. El usuario no tiene control sobre cuándo se llama al constructor estático. Si un constructor estático no es privado, se puede llamar mediante código que no sea CLR. Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado. El compilador de C# obliga a los constructores estáticos a ser privados.

❌ NO genere excepciones desde constructores estáticos.

Si se produce una excepción desde un constructor de tipos, el tipo no se puede usar en el dominio de aplicación actual.

✔️ considere la posibilidad de inicializar campos estáticos en línea en lugar de usar explícitamente constructores estáticos, porque el tiempo de ejecución puede optimizar el rendimiento de los tipos que no tienen un constructor estático definido explícitamente.

*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones para el diseño de miembros](member.md)
- [Directrices de diseño de marco](index.md)
