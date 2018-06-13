---
title: Valores (F#)
description: 'Obtenga información acerca de cómo los valores de F # son cantidades que tienen un tipo específico.'
ms.date: 05/16/2016
ms.openlocfilehash: 4d2874a694d9c39048a28827be858cba499dca87
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2018
ms.locfileid: "34149119"
---
# <a name="values"></a>Valores

Los valores de F# son cantidades que tienen un tipo específico. Los valores pueden ser números enteros o de punto flotante, caracteres o texto, listas, secuencias, matrices, tuplas, uniones discriminadas, registros, tipos de clase o valores de función.


## <a name="binding-a-value"></a>Enlace de un valor
El término *enlace* significa asociar un nombre a una definición. La palabra clave `let` enlaza un valor, como en los ejemplos siguientes:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet601.fs)]

El tipo de un valor se infiere de la definición. Para un tipo primitivo, como un número entero o de punto flotante, el tipo se determina a partir del tipo del literal. Por tanto, en el ejemplo anterior, el compilador infiere que el tipo de `b` es `unsigned int`, mientras que el compilador infiere que el tipo de `a` es `int`. El tipo de un valor de función se determina a partir del valor devuelto en el cuerpo de la función. Para más información sobre los tipos de valor de función, vea [Funciones](../functions/index.md). Para más información sobre los tipos literales, vea [Literals](../literals.md) (Literales).

El compilador no emite información de diagnóstico sobre los enlaces de forma predeterminada. Para recibir estos mensajes, habilitar la advertencia 1182 en el archivo de proyecto o al invocar el compilador (vea `--warnon` en [opciones del compilador](../compiler-options.md)).

## <a name="why-immutable"></a>¿Por qué inmutables?
Los valores inmutables son valores que no se pueden cambiar durante el transcurso de la ejecución de un programa. Si está habituado a usar lenguajes como C++, Visual Basic o C#, le resultará sorprendente que F# dé prioridad a los valores inmutables y no a las variables, a las que se pueden asignar nuevos valores durante la ejecución de un programa. Los datos inmutables son un elemento importante de la programación funcional. En un entorno multiproceso, resulta complicado administrar las variables mutables compartidas, dado que pueden modificarlas muchos subprocesos diferentes. Además, con las variables mutables, a veces puede resultar difícil saber si existe la posibilidad de que una variable haya cambiado cuando se pasa a otra función.

En los lenguajes funcionales puros, no hay variables y las funciones se comportan estrictamente como funciones matemáticas. Cuando el código de un lenguaje de procedimientos usa una asignación de variable para modificar un valor, el código equivalente de un lenguaje funcional tiene un valor inmutable que es la entrada, una función inmutable y distintos valores inmutables como salida. Esta rigidez matemática permite un razonamiento más estricto sobre el comportamiento del programa. Y este razonamiento más estricto es lo que permite a los compiladores comprobar el código de una manera más rigurosa y optimizar con mayor eficacia, además de hacer que a los desarrolladores de software les resulte más fácil entender y escribir código correcto. Por tanto, es probable que el código funcional sea más fácil de depurar que el código de procedimientos ordinario.

Aunque F# no es un lenguaje funcional puro, admite plenamente la programación funcional. El uso de valores inmutables es una práctica correcta porque permite que el código se beneficie de un aspecto importante de la programación funcional.


## <a name="mutable-variables"></a>Variables mutables
Se puede usar la palabra clave `mutable` para especificar una variable que se puede cambiar. En F#, en general las variables mutables deben tener un ámbito limitado, ya sea como campo de un tipo o bien como valor local. Las variables mutables con un ámbito limitado son más fáciles de controlar y es menos probable que se modifiquen de manera incorrecta.

Se puede asignar un valor inicial a una variable mutable mediante la palabra clave `let` de la misma manera que se define un valor. Pero la diferencia reside en que, posteriormente, se pueden asignar nuevos valores a las variables mutables mediante el operador `<-`, como en el ejemplo siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet602.fs)]

Los valores marcados `mutable` se puede promover automáticamente a `'a ref` si captura una clausura, incluidas las formas que crean los cierres, como `seq` generadores. Si desea recibir una notificación cuando esto ocurre, habilitar la advertencia 3180 en el archivo de proyecto o al invocar el compilador.
    
## <a name="related-topics"></a>Temas relacionados


|Título|Descripción|
|-----|-----------|
|[Enlaces let](../functions/let-bindings.md)|Proporciona información sobre el uso de la `let` palabra clave que se va a enlazar nombres a los valores y funciones.|
|[Funciones](../functions/index.md)|Proporciona información general sobre las funciones en F#.|

## <a name="see-also"></a>Vea también
[Valores NULL](null-Values.md)

[Referencia del lenguaje F#](../index.md)
