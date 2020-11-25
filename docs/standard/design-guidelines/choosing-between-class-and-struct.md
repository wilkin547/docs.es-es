---
title: Elegir entre clases y structs
description: Obtenga información sobre cómo decidir si diseñar un tipo como una clase o diseñar un tipo como un struct. Comprenda cómo se diferencian los tipos de referencia y los tipos de valor en .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
ms.openlocfilehash: 05ba9abbc9495d927b7f58ebb06f152c0c15772f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701255"
---
# <a name="choosing-between-class-and-struct"></a>Elegir entre clases y structs

Una de las decisiones de diseño básicas a las que se enfrenta cada diseñador de Marcos es si se debe diseñar un tipo como una clase (un tipo de referencia) o como un struct (un tipo de valor). Es fundamental comprender mejor las diferencias en el comportamiento de los tipos de referencia y los tipos de valor para tomar esta decisión.

 La primera diferencia entre los tipos de referencia y los tipos de valor que se deben tener en cuenta es que los tipos de referencia se asignan en el montón y se recolectan como elementos no utilizados, mientras que los tipos de valor se asignan en la pila o en línea en los tipos contenedores y se desasignan cuando se desenreda la pila o cuando se cancela la asignación del tipo contenedor. Por lo tanto, las asignaciones y desasignaciones de tipos de valor son en general más barata que las asignaciones y desasignaciones de tipos de referencia.

 A continuación, las matrices de tipos de referencia se asignan fuera de línea, lo que significa que los elementos de la matriz son simplemente referencias a las instancias del tipo de referencia que residen en el montón. Las matrices de tipos de valor se asignan en línea, lo que significa que los elementos de la matriz son las instancias reales del tipo de valor. Por lo tanto, las asignaciones y desasignaciones de matrices de tipos de valor son mucho más baratas que las asignaciones y desasignaciones de matrices de tipos de referencia. Además, en la mayoría de los casos, las matrices de tipos de valor presentan una ubicación de referencia mucho mejor.

 La diferencia siguiente está relacionada con el uso de memoria. Los tipos de valor se aplican a la conversión boxing cuando se convierten a un tipo de referencia o a una de las interfaces que implementan. Se les aplica la conversión unboxing cuando se convierten de nuevo al tipo de valor. Dado que los cuadros son objetos que se asignan en el montón y se recolectan como elementos no utilizados, demasiadas conversiones boxing y unboxing pueden tener un impacto negativo en el montón, el recolector de elementos no utilizados y, en última instancia, el rendimiento de la aplicación.  Por el contrario, no se produce ninguna conversión boxing cuando se convierten tipos de referencia. (Para obtener más información, vea [conversión boxing y conversión unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).

 A continuación, las asignaciones de tipos de referencia copian la referencia, mientras que las asignaciones de tipos de valor copian el valor completo. Por lo tanto, las asignaciones de tipos de referencia grandes son más baratas que las asignaciones de tipos de valores grandes.

 Por último, los tipos de referencia se pasan por referencia, mientras que los tipos de valor se pasan por valor. Los cambios en una instancia de un tipo de referencia afectan a todas las referencias que señalan a la instancia. Las instancias de tipo de valor se copian cuando se pasan por valor. Cuando se cambia una instancia de un tipo de valor, no afecta a ninguna de sus copias. Dado que el usuario no crea las copias explícitamente, pero se crean implícitamente cuando se pasan argumentos o se devuelven valores, los tipos de valor que se pueden cambiar pueden resultar confusos para muchos usuarios. Por lo tanto, los tipos de valor deben ser inmutables.

 Como regla general, la mayoría de los tipos de un marco de trabajo deben ser clases. Sin embargo, hay algunas situaciones en las que las características de un tipo de valor hacen que sea más apropiado usar estructuras.

 ✔️ considere la posibilidad de definir un struct en lugar de una clase si las instancias del tipo son pequeñas y suelen ser de corta duración o se incrustan normalmente en otros objetos.

 ❌ Evite definir un struct a menos que el tipo tenga todas las características siguientes:

- Representa lógicamente un valor único, similar a los tipos primitivos ( `int` , `double` , etc.).

- Tiene un tamaño de instancia inferior a 16 bytes.

- Es inmutable.

- No será necesario aplicar la conversión boxing a menudo.

 En todos los demás casos, debe definir los tipos como clases.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de tipos](type.md)
- [Directrices de diseño de marco](index.md)
