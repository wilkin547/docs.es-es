---
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: d1778e2bb58d32e976f10b3fba1637918278d36e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409288"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variable de objeto o de bloque With no establecida
Se está haciendo referencia a una variable de objeto no válido.   Este error puede producirse por varias razones:

- Se declaró una variable sin especificar un tipo. Si una variable se declara sin especificar un tipo, el valor predeterminado es Type `Object` .

    Por ejemplo, una variable declarada con `Dim x` sería de tipo `Object;` una variable declarada con `Dim x As String` sería de tipo `String` .

    > [!TIP]
    > La `Option Strict` instrucción no permite tipos implícitos que generan un `Object` tipo. Si omite el tipo, se producirá un error en tiempo de compilación. Vea [Option Strict (instrucción)](../statements/option-strict-statement.md).

- Está intentando hacer referencia a un objeto que se ha establecido en `Nothing` .

- Está intentando obtener acceso a un elemento de una variable de matriz que no se ha declarado correctamente.

    Por ejemplo, una matriz declarada como `products() As String` desencadenará el error si se intenta hacer referencia a un elemento de la matriz `products(3) = "Widget"` . La matriz no tiene elementos y se trata como un objeto.

- Está intentando obtener acceso al código dentro de un `With...End With` bloque antes de que se haya inicializado el bloque.   Un `With...End With` bloque se debe inicializar ejecutando el punto de `With` entrada de la instrucción.

> [!NOTE]
> En versiones anteriores de Visual Basic o VBA, este error también se desencadenaba asignando un valor a una variable sin usar la `Set` palabra clave ( `x = "name"` en lugar de `Set x = "name"` ). La `Set` palabra clave ya no es válida en Visual Basic .net.

## <a name="to-correct-this-error"></a>Para corregir este error

1. Establezca `Option Strict` en agregando `On` el código siguiente al principio del archivo:

    ```vb
    Option Strict On
    ```

    Al ejecutar el proyecto, aparecerá un error del compilador en el **lista de errores** para cualquier variable que se especificó sin un tipo.

2. Si no desea habilitar `Option Strict` , busque en el código las variables que se especificaron sin un tipo ( `Dim x` en lugar de `Dim x As String` ) y agregue el tipo previsto a la declaración.

3. Asegúrese de que no hace referencia a una variable de objeto que se ha establecido en `Nothing` .  Busque en el código la palabra clave `Nothing` y revise el código para que el objeto no se establezca en `Nothing` hasta que se haya hecho referencia a él.

4. Asegúrese de que las variables de matriz se dimensionan antes de tener acceso a ellas. Puede asignar una dimensión la primera vez que cree la matriz ( `Dim x(5) As String` en lugar de `Dim x() As String` ), o bien use la `ReDim` palabra clave para establecer las dimensiones de la matriz antes de tener acceso a ella por primera vez.

5. Asegúrese de que el `With` bloque se inicializa ejecutando el punto de `With` entrada de la instrucción.

## <a name="see-also"></a>Consulte también

- [Declaración de variables de objeto](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [Instrucción ReDim](../statements/redim-statement.md)
- [Instrucción With...End With](../statements/with-end-with-statement.md)
