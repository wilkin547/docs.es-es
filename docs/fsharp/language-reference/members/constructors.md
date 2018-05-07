---
title: Constructores (F#)
description: 'Obtener información sobre cómo definir y utilizar constructores en F # para crear e inicializar objetos de clase y estructura.'
ms.date: 05/16/2016
ms.openlocfilehash: 1773c111e0398aa83951afe14979d8a4ebc4907f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="constructors"></a>Constructores

En este tema se describe cómo definir y utilizar los constructores para crear e inicializar objetos de clase y estructura.


## <a name="construction-of-class-objects"></a>Construcción de objetos de clase
Objetos de tipos de clase tienen constructores. Hay dos tipos de constructores. Uno es el constructor primario, cuyos parámetros aparecen entre paréntesis justo después del nombre de tipo. Especificar otros constructores adicionales opcionales mediante la `new` palabra clave. Todos estos constructores adicionales deben llamar al constructor primario.

El constructor primario contiene `let` y `do` enlaces que aparecen al principio de la definición de clase. A `let` enlace declara campos privados y los métodos de la clase; un `do` enlace ejecuta código. Para obtener más información acerca de `let` enlaces en los constructores de clase, consulte [ `let` enlaces en clases](let-bindings-in-classes.md). Para obtener más información acerca de `do` enlaces en los constructores, vea [ `do` enlaces en clases](do-bindings-in-classes.md).

Independientemente de si el constructor que desea llamar es un constructor primario o un constructor adicional, puede crear objetos mediante un `new` expresión, con o sin la parte opcional `new` palabra clave. Inicializar los objetos junto con los argumentos de constructor, ya sea mediante la lista de los argumentos en orden y separados por comas y entre paréntesis, o mediante el uso de argumentos con nombre y los valores entre paréntesis. También puede establecer propiedades en un objeto durante la construcción del objeto mediante el uso de los nombres de propiedad y asignar los valores tal y como se utiliza con nombre argumentos de constructor.

El código siguiente muestra una clase que tiene un constructor y varias maneras de crear objetos.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

La salida es la siguiente.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Construcción de estructuras
Las estructuras siguen todas las reglas de clases. Por lo tanto, puede tener un constructor primario, y puede proporcionar constructores adicionales mediante `new`. Sin embargo, hay una diferencia importante entre las estructuras y clases: las estructuras pueden tener un constructor predeterminado (es decir, uno sin argumentos), aunque se haya definido ningún constructor primario. El constructor predeterminado inicializa todos los campos en el valor predeterminado para ese tipo, normalmente cero o su equivalente. Los constructores que se definen para las estructuras de deben tener al menos un argumento para que no entren en conflicto con el constructor predeterminado.

Además, las estructuras suelen tienen campos que se crean mediante el `val` palabra clave; las clases también pueden tener estos campos. Estructuras y clases que tienen campos definidos mediante el `val` palabra clave también se puede inicializar en constructores adicionales mediante expresiones de registro, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Para obtener más información, consulte [campos explícitos: el `val` palabra clave](explicit-fields-the-val-keyword.md).


## <a name="executing-side-effects-in-constructors"></a>Ejecutar efectos secundarios en constructores
Un constructor primario en una clase puede ejecutar código en un `do` enlace. Sin embargo, ¿qué ocurre si tiene que ejecutar el código en un constructor adicional, sin un `do` enlace? Para ello, use la `then` palabra clave.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Los efectos secundarios del constructor primario seguir ejecutándose. Por lo tanto, el resultado es como sigue.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>Autoidentificadores en constructores
En otros miembros, proporcione un nombre para el objeto actual en la definición de cada miembro. También puede colocar el identificador propio en la primera línea de la definición de clase mediante el uso de la `as` palabra clave inmediatamente después de los parámetros del constructor. En el ejemplo siguiente se muestra esta sintaxis.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

En los constructores adicionales, también puede definir un identificador propio colocando el `as` cláusula justo después de los parámetros del constructor. En el ejemplo siguiente se muestra esta sintaxis.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Pueden producirse problemas al intentar utilizar un objeto antes de definirla por completo. Por lo tanto, los usos del propio identificador pueden causar el compilador emite una advertencia e inserte comprobaciones adicionales para asegurarse de que no se tiene acceso a los miembros de un objeto antes de que se inicialice el objeto. Sólo se debe utilizar el identificador propio en el `do` enlaces del constructor primario o después de la `then` palabra clave en los constructores adicionales.

El nombre del propio identificador no tiene que ser `this`. Puede ser cualquier identificador válido.


## <a name="assigning-values-to-properties-at-initialization"></a>Asignar valores a propiedades en la inicialización
Puede asignar valores a las propiedades de un objeto de clase en el código de inicialización mediante la anexión de una lista de asignaciones del formulario `property = value` a la lista de argumentos para un constructor. Esto se muestra en el ejemplo de código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

La versión siguiente del código anterior muestra la combinación de argumentos ordinarios, argumentos opcionales y configuración de propiedades de una llamada de constructor.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a>Constructores de clase heredada
Al heredar de una clase base que tiene un constructor, debe especificar sus argumentos en la cláusula de heredar. Para obtener más información, consulte [constructores y herencia](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Constructores estáticos o constructores de tipo
Además de especificar código para crear objetos, estáticos `let` y `do` enlaces se pueden crear en tipos de clase que se ejecutan antes de que el tipo en primer lugar se utiliza para realizar la inicialización en el nivel de tipo. Para obtener más información, consulte [ `let` enlaces en clases](let-bindings-in-classes.md) y [ `do` enlaces en clases](do-bindings-in-classes.md).

## <a name="see-also"></a>Vea también
[Miembros](index.md)
