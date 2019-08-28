---
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040551"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Variable de objeto o de bloque With no establecida
Se está haciendo referencia a una variable de objeto no válido.   Este error puede producirse por varias razones:

- Se declaró una variable sin especificar un tipo. Si una variable se declara sin especificar un tipo, el valor predeterminado es Type `Object`.

    Por ejemplo, una `Dim x` variable declarada con sería de tipo `Object;` una variable declarada con `Dim x As String` sería `String`de tipo.

    > [!TIP]
    > La `Option Strict` instrucción no permite tipos implícitos que generan un `Object` tipo. Si omite el tipo, se producirá un error en tiempo de compilación. Consulte [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).

- Está intentando hacer referencia a un objeto que se ha establecido en `Nothing`.

- Está intentando obtener acceso a un elemento de una variable de matriz que no se ha declarado correctamente.

    Por ejemplo, una matriz declarada como `products() As String` desencadenará el error si se intenta hacer referencia a un elemento de la matriz. `products(3) = "Widget"` La matriz no tiene elementos y se trata como un objeto.

- Está intentando obtener acceso al código dentro de `With...End With` un bloque antes de que se haya inicializado el bloque.   Un `With...End With` bloque se debe inicializar ejecutando el punto de `With` entrada de la instrucción.

> [!NOTE]
> En versiones anteriores de Visual Basic o VBA, este error también se desencadenaba asignando un valor a una variable sin usar la `Set` palabra clave (`x = "name"` en lugar de `Set x = "name"`). La `Set` palabra clave ya no es válida en Visual Basic .net.

## <a name="to-correct-this-error"></a>Para corregir este error

1. Establezca `Option Strict` en`On` agregando el código siguiente al principio del archivo:

    ```vb
    Option Strict On
    ```

    Al ejecutar el proyecto, aparecerá un error del compilador en el **lista de errores** para cualquier variable que se especificó sin un tipo.

2. Si no desea habilitar `Option Strict`, busque en el código las variables que se especificaron sin un tipo (`Dim x` en lugar de `Dim x As String`) y agregue el tipo previsto a la declaración.

3. Asegúrese de que no hace referencia a una variable de objeto que se ha `Nothing`establecido en.  Busque en el código la palabra `Nothing`clave y revise el código para que el objeto no se establezca en `Nothing` hasta que se haya hecho referencia a él.

4. Asegúrese de que las variables de matriz se dimensionan antes de tener acceso a ellas. Puede asignar una dimensión la primera vez que cree la matriz (`Dim x(5) As String` en lugar de `Dim x() As String`), o bien use la `ReDim` palabra clave para establecer las dimensiones de la matriz antes de tener acceso a ella por primera vez.

5. Asegúrese de que `With` el bloque se inicializa ejecutando el punto de `With` entrada de la instrucción.

## <a name="see-also"></a>Vea también

- [Declaración de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
- [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
