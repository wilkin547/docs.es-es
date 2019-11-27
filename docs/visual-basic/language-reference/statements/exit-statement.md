---
title: Exit (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1bfe81428fd3c50663fd8978e05c6a945cd47df8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345936"
---
# <a name="exit-statement-visual-basic"></a>Exit (Instrucción, Visual Basic)

Sale de un procedimiento o un bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o la definición del bloque.

## <a name="syntax"></a>Sintaxis

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Instrucciones

 `Exit Do`  
 Sale inmediatamente del bucle `Do` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `Loop`. `Exit Do` solo se puede usar dentro de un bucle de `Do`. Cuando se usa dentro de bucles `Do` anidados, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

 `Exit For`  
 Sale inmediatamente del bucle `For` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `Next`. `Exit For` solo se puede usar dentro de un bucle `For`...`Next` o `For Each`...`Next`. Cuando se usa dentro de bucles `For` anidados, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

 `Exit Function`  
 Sale inmediatamente del procedimiento de `Function` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Function`. `Exit Function` solo se puede usar dentro de un procedimiento `Function`.

 Para especificar un valor devuelto, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Function`. Para asignar el valor devuelto y salir de la función en una instrucción, en su lugar puede usar la [instrucción return](return-statement.md).

 `Exit Property`  
 Sale inmediatamente del procedimiento de `Property` en el que aparece. La ejecución continúa con la instrucción que llamó al procedimiento `Property`, es decir, con la instrucción que solicita o establece el valor de la propiedad. `Exit Property` solo se puede usar dentro del procedimiento de `Get` o `Set` de una propiedad.

 Para especificar un valor devuelto en un procedimiento `Get`, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Property`. Para asignar el valor devuelto y salir del procedimiento `Get` en una instrucción, en su lugar puede usar la instrucción `Return`.

 En un procedimiento de `Set`, la instrucción `Exit Property` es equivalente a la instrucción `Return`.

 `Exit Select`  
 Sale inmediatamente del bloque `Select Case` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `End Select`. `Exit Select` solo se puede usar dentro de una instrucción de `Select Case`.

 `Exit Sub`  
 Sale inmediatamente del procedimiento de `Sub` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Sub`. `Exit Sub` solo se puede usar dentro de un procedimiento `Sub`.

 En un procedimiento de `Sub`, la instrucción `Exit Sub` es equivalente a la instrucción `Return`.

 `Exit Try`  
 Sale inmediatamente del bloque `Try` o `Catch` en el que aparece. La ejecución continúa con el bloque `Finally` si hay alguno, o con la instrucción que sigue a la instrucción `End Try` de lo contrario. `Exit Try` solo se puede usar dentro de un bloque de `Try` o `Catch` y no dentro de un bloque de `Finally`.

 `Exit While`  
 Sale inmediatamente del bucle `While` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `End While`. `Exit While` solo se puede usar dentro de un bucle de `While`. Cuando se usa dentro de bucles `While` anidados, `Exit While` transfiere el control al bucle que está un nivel anidado por encima del bucle donde se produce `Exit While`.

## <a name="remarks"></a>Comentarios

No confunda `Exit` instrucciones con instrucciones de `End`. `Exit` no define el final de una instrucción.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la condición de bucle detiene el bucle cuando la variable de `index` es mayor que 100. Sin embargo, la instrucción `If` del bucle hace que la instrucción `Exit Do` detenga el bucle cuando la variable de índice sea mayor que 10.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction`y, a continuación, se usa `Exit Function` para devolver de la función:

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la [instrucción return](return-statement.md) para asignar el valor devuelto y salir de la función:

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>Vea también

- [Continue (instrucción)](continue-statement.md)
- [Do...Loop (instrucción)](do-loop-statement.md)
- [End (instrucción)](end-statement.md)
- [For Each...Next (instrucción)](for-each-next-statement.md)
- [For...Next (instrucción)](for-next-statement.md)
- [Function (instrucción)](function-statement.md)
- [Return (instrucción)](return-statement.md)
- [Stop (instrucción)](stop-statement.md)
- [Sub (instrucción)](sub-statement.md)
- [Try...Catch...Finally (instrucción)](try-catch-finally-statement.md)
