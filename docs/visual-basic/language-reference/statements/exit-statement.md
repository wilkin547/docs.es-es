---
title: Exit (Instrucción, Visual Basic)
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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956944"
---
# <a name="exit-statement-visual-basic"></a>Exit (Instrucción, Visual Basic)

Sale de un procedimiento o un bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o la definición del bloque.

## <a name="syntax"></a>Sintaxis

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Instrucciones

 `Exit Do`  
 Sale inmediatamente del bucle `Do` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `Loop`. `Exit Do` solo se puede usar dentro de un bucle `Do`. Cuando se usa dentro de bucles `Do` anidados, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

 `Exit For`  
 Sale inmediatamente del bucle `For` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `Next`. `Exit For` solo se puede usar dentro de un bucle `For`... `Next` o `For Each`... `Next`. Cuando se usa dentro de bucles `For` anidados, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

 `Exit Function`  
 Sale inmediatamente del procedimiento `Function` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Function`. `Exit Function` solo se puede usar dentro de un procedimiento `Function`.

 Para especificar un valor devuelto, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Function`. Para asignar el valor devuelto y salir de la función en una instrucción, en su lugar puede usar la [instrucción return](return-statement.md).

 `Exit Property`  
 Sale inmediatamente del procedimiento `Property` en el que aparece. La ejecución continúa con la instrucción que llamó al procedimiento `Property`, es decir, con la instrucción que solicita o establece el valor de la propiedad. `Exit Property` solo se puede usar dentro del procedimiento `Get` o `Set` de una propiedad.

 Para especificar un valor devuelto en un procedimiento `Get`, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Property`. Para asignar el valor devuelto y salir del procedimiento `Get` en una instrucción, puede usar en su lugar la instrucción `Return`.

 En un procedimiento `Set`, la instrucción `Exit Property` es equivalente a la instrucción `Return`.

 `Exit Select`  
 Sale inmediatamente del bloque `Select Case` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `End Select`. `Exit Select` solo se puede usar dentro de una instrucción `Select Case`.

 `Exit Sub`  
 Sale inmediatamente del procedimiento `Sub` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Sub`. `Exit Sub` solo se puede usar dentro de un procedimiento `Sub`.

 En un procedimiento `Sub`, la instrucción `Exit Sub` es equivalente a la instrucción `Return`.

 `Exit Try`  
 Sale inmediatamente del bloque `Try` o `Catch` en el que aparece. La ejecución continúa con el bloque `Finally`, si hay alguno, o con la instrucción que sigue a la instrucción `End Try` en caso contrario. `Exit Try` solo se puede usar dentro de un bloque `Try` o `Catch` y no dentro de un bloque `Finally`.

 `Exit While`  
 Sale inmediatamente del bucle `While` en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción `End While`. `Exit While` solo se puede usar dentro de un bucle `While`. Cuando se usa en bucles `While` anidados, `Exit While` transfiere el control al bucle que está un nivel anidado por encima del bucle donde se produce `Exit While`.

## <a name="remarks"></a>Comentarios

No confunda las instrucciones `Exit` con las instrucciones `End`. `Exit` no define el final de una instrucción.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la condición de bucle detiene el bucle cuando la variable `index` es mayor que 100. La instrucción `If` del bucle, sin embargo, hace que la instrucción `Exit Do` detenga el bucle cuando la variable de índice sea mayor que 10.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, se usa `Exit Function` para volver de la función:

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
