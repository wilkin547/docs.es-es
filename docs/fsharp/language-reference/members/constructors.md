---
title: Constructores
description: 'Obtenga información sobre cómo definir y usar constructores en F # para crear e inicializar objetos de clase y estructura.'
ms.date: 05/16/2016
ms.openlocfilehash: be8fc3f1d82a9a7c778a6d094139f14150a28813
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303444"
---
# <a name="constructors"></a>Constructores

En este artículo se describe cómo definir y usar constructores para crear e inicializar objetos de clase y estructura.

## <a name="construction-of-class-objects"></a>Construcción de objetos de clase

Los objetos de tipos de clase tienen constructores. Hay dos tipos de constructores. Uno es el constructor principal, cuyos parámetros aparecen entre paréntesis justo después del nombre de tipo. Especifique otros constructores adicionales opcionales mediante la `new` palabra clave. Cualquier constructor adicional de este tipo debe llamar al constructor principal.

El constructor principal contiene `let` `do` enlaces y que aparecen al principio de la definición de clase. Un `let` enlace declara los campos y métodos privados de la clase; un `do` enlace ejecuta código. Para obtener más información sobre los `let` enlaces de los constructores de clase, vea [ `let` enlaces en clases](let-bindings-in-classes.md). Para obtener más información sobre los `do` enlaces en constructores, vea [ `do` enlaces en clases](do-bindings-in-classes.md).

Independientemente de si el constructor al que desea llamar es un constructor principal o un constructor adicional, puede crear objetos mediante una `new` expresión, con o sin la `new` palabra clave opcional. Los objetos se inicializan junto con los argumentos del constructor, ya sea mediante una lista de los argumentos en orden y se separan mediante comas y entre paréntesis, o usando argumentos y valores con nombre entre paréntesis. También puede establecer las propiedades de un objeto durante la construcción del objeto utilizando los nombres de propiedad y asignando valores de la misma forma que se usan los argumentos del constructor con nombre.

En el código siguiente se muestra una clase que tiene un constructor y varias maneras de crear objetos:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

La salida es como sigue:

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Construcción de estructuras

Las estructuras siguen todas las reglas de las clases. Por lo tanto, puede tener un constructor principal y puede proporcionar constructores adicionales mediante `new` . Sin embargo, hay una diferencia importante entre las estructuras y las clases: las estructuras pueden tener un constructor sin parámetros (es decir, uno sin argumentos) aunque no se haya definido ningún constructor principal. El constructor sin parámetros inicializa todos los campos en el valor predeterminado de ese tipo, normalmente cero o su equivalente. Los constructores que defina para las estructuras deben tener al menos un argumento para que no entren en conflicto con el constructor sin parámetros.

Además, las estructuras suelen tener campos que se crean mediante la `val` palabra clave; las clases también pueden tener estos campos. Las estructuras y las clases que tienen campos definidos mediante la `val` palabra clave también se pueden inicializar en constructores adicionales mediante el uso de expresiones de registro, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Para obtener más información, vea [campos explícitos: la `val` palabra clave](explicit-fields-the-val-keyword.md).

## <a name="executing-side-effects-in-constructors"></a>Ejecutar efectos secundarios en constructores

Un constructor principal de una clase puede ejecutar código en un `do` enlace. Sin embargo, ¿qué ocurre si tiene que ejecutar código en un constructor adicional, sin un `do` enlace? Para ello, use la `then` palabra clave.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Los efectos secundarios del constructor principal todavía se ejecutan. Por lo tanto, la salida es la siguiente:

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

La razón por la `then` que se requiere, en lugar de otra, `do` es que la `do` palabra clave tiene su significado estándar para delimitar una `unit` expresión de devolución cuando está presente en el cuerpo de un constructor adicional. Solo tiene un significado especial en el contexto de los constructores principales.

## <a name="self-identifiers-in-constructors"></a>Identificadores propios en constructores

En otros miembros, se proporciona un nombre para el objeto actual en la definición de cada miembro. También puede colocar el identificador propio en la primera línea de la definición de clase mediante la `as` palabra clave inmediatamente después de los parámetros del constructor. En el ejemplo siguiente se muestra esta sintaxis.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

En los constructores adicionales, también puede definir un identificador propio colocando la `as` cláusula justo después de los parámetros del constructor. En el ejemplo siguiente se muestra esta sintaxis:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Pueden producirse problemas al intentar usar un objeto antes de que se defina por completo. Por lo tanto, los usos del propio identificador pueden hacer que el compilador emita una advertencia e inserte comprobaciones adicionales para asegurarse de que no se tiene acceso a los miembros de un objeto antes de que se inicialice el objeto. Solo se debe usar el identificador propio en los `do` enlaces del constructor principal o después de la `then` palabra clave en constructores adicionales.

No es necesario que el nombre del propio identificador sea `this` . Puede ser cualquier identificador válido.

## <a name="assigning-values-to-properties-at-initialization"></a>Asignar valores a propiedades en la inicialización

Puede asignar valores a las propiedades de un objeto de clase en el código de inicialización anexando una lista de asignaciones del formulario `property = value` a la lista de argumentos de un constructor. Esto se muestra en el ejemplo de código siguiente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

La siguiente versión del código anterior muestra la combinación de argumentos ordinarios, argumentos opcionales y valores de propiedad en una llamada de constructor:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a>Constructores en la clase heredada

Al heredar de una clase base que tiene un constructor, debe especificar sus argumentos en la cláusula inherit. Para obtener más información, vea [constructores y herencia](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Constructores estáticos o constructores de tipo

Además de especificar el código para crear objetos, `let` se pueden crear enlaces estáticos y `do` en tipos de clase que se ejecutan antes de que el tipo se use por primera vez para realizar la inicialización en el nivel de tipo. Para obtener más información, vea [ `let` enlaces en clases](let-bindings-in-classes.md) y [ `do` enlaces en clases](do-bindings-in-classes.md).

## <a name="see-also"></a>Consulte también

- [Miembros](index.md)
