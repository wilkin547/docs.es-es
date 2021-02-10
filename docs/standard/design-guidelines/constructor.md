---
description: 'Más información acerca de: Diseño de constructores'
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
ms.openlocfilehash: 2a5c85e1dea3349f897c24fa5d40d73c6e1f9d7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642323"
---
# <a name="constructor-design"></a>Diseño de constructores

Hay dos tipos de constructores: constructores de tipo y constructores de instancia.

Los constructores de tipo son estáticos y los ejecuta CLR antes de que se use el tipo. Los constructores de instancias se ejecutan cuando se crea una instancia de un tipo.

Los constructores de tipo no pueden tomar ningún parámetro, pero los constructores de instancias sí que pueden hacerlo. Los constructores de instancias que no toman ningún parámetro se suelen denominar "constructores sin parámetros".

Los constructores son la manera más natural de crear instancias de un tipo. La mayoría de los desarrolladores buscarán e intentarán usar un constructor antes de plantearse usar formas alternativas de crear instancias (por ejemplo, Factory Method).

✔️ Recomendamos proporcionar constructores simples, idealmente de forma predeterminada.

Un constructor simple tiene un número muy pequeño de parámetros, y todos los parámetros son primitivos o enumeraciones. Estos constructores simples aumentan la facilidad de uso del marco.

✔️ Recomendamos usar un método Factory Method estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si las instrucciones de diseño de constructores no son naturales.

✔️ Use parámetros de constructor como accesos directos para establecer las propiedades principales.

En la semántica no debería haber ninguna diferencia entre el uso del constructor vacío seguido de algunos conjuntos de propiedades y el uso de un constructor con varios argumentos.

✔️ Use el mismo nombre para los parámetros del constructor y una propiedad si los parámetros del constructor se utilizan simplemente para establecer la propiedad.

La única diferencia entre estos parámetros y las propiedades debe ser el uso de mayúsculas y minúsculas.

✔️ Realice un trabajo mínimo en el constructor.

Los constructores no deberían hacer mucho más que capturar los parámetros del constructor. El costo de cualquier otro procesamiento debe retrasarse hasta que sea necesario.

✔️ Genere excepciones desde constructores de instancias, si es necesario.

✔️ Declare explícitamente el constructor sin parámetros público en las clases, si se requiere este tipo de constructor.

Si no declara explícitamente ningún constructor en un tipo, muchos lenguajes (como C# ) agregarán automáticamente un constructor sin parámetros público. Las clases abstractas obtienen un constructor protegido.

Al agregar un constructor con parámetros a una clase, se impide que el compilador agregue el constructor sin parámetros. Esto suele provocar cambios importantes de forma accidental.

❌ EVITE definir explícitamente constructores sin parámetros en estructuras.

Gracias a esto, la creación de matrices es más rápida, ya que si no se define el constructor sin parámetros, no es necesario que se ejecute en cada ranura de la matriz. Tenga en cuenta que muchos compiladores, incluido C#, no permiten que las estructuras tengan constructores sin parámetros por esta razón.

❌ EVITE llamar a miembros virtuales en un objeto dentro de su constructor.

Al llamar a un miembro virtual, se provocará que se llame a la invalidación más derivada, incluso si el constructor del tipo más derivado aún no se ha ejecutado completamente.

## <a name="type-constructor-guidelines"></a>Instrucciones de constructores de tipo

✔️ Haga que los constructores estáticos sean privados.

Un constructor estático, también denominado "constructor de clase", se usa para inicializar un tipo. CLR llama al constructor estático antes de crear la primera instancia del tipo o antes de llamar a cualquier miembro estático. El usuario no tiene control sobre cuándo se llama al constructor estático. Si un constructor estático no es privado, se puede llamar a través de un código distinto del de CLR. En función de las operaciones que se realizan en el constructor, esto puede producir un comportamiento inesperado. El compilador de C# fuerza a los constructores estáticos a que sean privados.

❌ NO genere excepciones desde constructores estáticos.

Si se inicia una excepción desde un constructor de tipo, el tipo no se podrá usar en el dominio de aplicación actual.

✔️ Recomendamos inicializar campos estáticos en línea en lugar de usar explícitamente constructores estáticos, porque el runtime puede optimizar el rendimiento de los tipos que no tienen un constructor estático definido explícitamente.

*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
