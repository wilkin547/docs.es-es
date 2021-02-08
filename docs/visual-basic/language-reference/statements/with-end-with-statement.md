---
description: 'Más información sobre: con... End with (instrucción Visual Basic)'
title: Instrucción With...End With
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: 86393d5dee7a03b2b8396b34b31326d1b0ea3c28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787570"
---
# <a name="withend-with-statement-visual-basic"></a>With...End With (Instrucción, Visual Basic)

Ejecuta una serie de instrucciones que hacen referencia repetidamente a un único objeto o estructura, por lo que las instrucciones pueden utilizar una sintaxis simplificada al acceder a los miembros del objeto o estructura.  Cuando use una estructura, sola podrá leer los valores de los miembros o invocar métodos, y recibirá un error si intenta asignar valores a los miembros de una estructura utilizada en una instrucción `With...End With`.

## <a name="syntax"></a>Sintaxis

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`objectExpression`|Obligatorio. Una expresión que se evalúa como un objeto. La expresión puede ser arbitrariamente compleja y se evalúa solo una vez. La expresión se puede evaluar como cualquier tipo de datos, incluidos los tipos elementales.|
|`statements`|Opcional. Una o varias instrucciones entre `With` y `End With` que pueden hacer referencia a los miembros de un objeto generado por la evaluación de `objectExpression`.|
|`End With`|Necesario. Termina la definición del bloque `With`.|

## <a name="remarks"></a>Observaciones

Con `With...End With`, puede ejecutar una serie de instrucciones en un objeto especificado sin necesidad especificar el nombre del objeto varias veces. En un bloque de instrucciones `With`, puede especificar un miembro del objeto que comience por un punto, como si el objeto de la instrucción `With` lo precediera.

Por ejemplo, para cambiar varias propiedades de un único objeto, coloque las instrucciones de asignación de las propiedades dentro del bloque `With...End With` y haga referencia al objeto una vez, en lugar de hacerlo en cada una de las asignaciones de las propiedades.

Si el código tiene acceso al mismo objeto en varias instrucciones, la instrucción `With` le brinda las ventajas siguientes:

- No es necesario evaluar varias veces una expresión compleja ni asignar el resultado a una variable temporal para hacer referencia a sus miembros varias veces.

- El código resulta más legible al eliminar expresiones de calificación repetitivas.

El tipo de datos de `objectExpression` puede ser cualquier tipo de clase o estructura, o incluso un tipo elemental de Visual Basic, como `Integer`.  Si `objectExpression` produce un valor que no es un objeto, solo podrá leer los valores de sus miembros o invocar métodos, y recibirá un error si intenta asignar valores a los miembros de una estructura utilizada en una instrucción `With...End With`.  Este es el mismo error que obtendría si invocara un método que devolviera una estructura y accediera inmediatamente a un miembro del resultado de la función, como `GetAPoint().x = 1`, y le asignara un valor.  El problema en ambos casos es que la estructura solo existe en la pila de llamadas y no hay forma de que un miembro de la estructura modificada en estas situaciones pueda escribir en una ubicación de forma que cualquier otro código del programa pueda observar el cambio.

`objectExpression` se evalúa una vez, tras su entrada en el bloque. No se puede reasignar `objectExpression` desde el interior del bloque `With`.

En un bloque `With`, solo de puede acceder a los métodos y propiedades del objeto especificado sin calificarlos. Se pueden usar métodos y propiedades de otros objetos, pero es necesario calificarlos con los nombres de objeto.

Puede incluir una instrucción `With...End With` dentro de otra. Las instrucciones `With...End With` anidadas pueden resultar confusas si los objetos a los que se hace referencia no están claros por el contexto. Debe proporcionar una referencia completa a un objeto que esté en un bloque `With` externo cuando se haga referencia al objeto desde dentro de un bloque `With` interno.

No se pueden crear bifurcaciones en un bloque de instrucciones `With` desde fuera del bloque.

A menos que el bloque contenga un bucle, las instrucciones se ejecutan una sola vez. Puede anidar diferentes tipos de estructuras de control. Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).

> [!NOTE]
> La palabra clave `With` también se puede usar en inicializadores de objeto. Para obtener más información y ejemplos, vea [inicializadores de objeto: tipos con nombre y anónimos](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) y [tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).
>
> Si usa un bloque `With` solo para inicializar las propiedades o campos de un objeto del que acaba de crear instancias, considere la posibilidad de utilizar en su lugar un inicializador de objetos.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, cada bloque `With` ejecuta una serie de instrucciones en un único objeto.

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se anidan las instrucciones `With…End With`. En la instrucción `With` anidada, la sintaxis hace referencia al objeto interno.

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic.List%601>
- [Estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Inicializadores de objeto: tipos con nombre y anónimos](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
