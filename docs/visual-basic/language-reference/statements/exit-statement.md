---
description: 'Más información sobre: Exit Statement (Visual Basic)'
title: Instrucción Exit
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
ms.openlocfilehash: 54af7fbf908dbad829cf6f08bf442dfe85e35610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769134"
---
# <a name="exit-statement-visual-basic"></a>Exit (Instrucción, Visual Basic)

Sale de un procedimiento o un bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o la definición del bloque.

## <a name="syntax"></a>Sintaxis

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Instrucciones

 `Exit Do`  
 Sale inmediatamente del `Do` bucle en el que aparece. La ejecución continúa con la instrucción que sigue a la `Loop` instrucción. `Exit Do` solo se puede usar dentro de un `Do` bucle. Cuando se usa dentro de `Do` bucles anidados, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

 `Exit For`  
 Sale inmediatamente del `For` bucle en el que aparece. La ejecución continúa con la instrucción que sigue a la `Next` instrucción. `Exit For` solo se puede usar dentro de un `For` bucle... `Next` o `For Each` ... `Next` . Cuando se usa dentro de `For` bucles anidados, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

 `Exit Function`  
 Sale inmediatamente del `Function` procedimiento en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó al `Function` procedimiento. `Exit Function` solo se puede usar dentro de un `Function` procedimiento.

 Para especificar un valor devuelto, puede asignar el valor al nombre de la función en una línea antes de la `Exit Function` instrucción. Para asignar el valor devuelto y salir de la función en una instrucción, en su lugar puede usar la [instrucción return](return-statement.md).

 `Exit Property`  
 Sale inmediatamente del `Property` procedimiento en el que aparece. La ejecución continúa con la instrucción que llamó al `Property` procedimiento, es decir, con la instrucción que solicita o establece el valor de la propiedad. `Exit Property` solo se puede usar dentro del procedimiento o de una propiedad `Get` `Set` .

 Para especificar un valor devuelto en un `Get` procedimiento, puede asignar el valor al nombre de la función en una línea antes de la `Exit Property` instrucción. Para asignar el valor devuelto y salir del `Get` procedimiento en una instrucción, en su lugar puede usar la `Return` instrucción.

 En un `Set` procedimiento, la `Exit Property` instrucción es equivalente a la `Return` instrucción.

 `Exit Select`  
 Sale inmediatamente del `Select Case` bloque en el que aparece. La ejecución continúa con la instrucción que sigue a la `End Select` instrucción. `Exit Select` solo se puede utilizar dentro de una `Select Case` instrucción.

 `Exit Sub`  
 Sale inmediatamente del `Sub` procedimiento en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó al `Sub` procedimiento. `Exit Sub` solo se puede usar dentro de un `Sub` procedimiento.

 En un `Sub` procedimiento, la `Exit Sub` instrucción es equivalente a la `Return` instrucción.

 `Exit Try`  
 Sale inmediatamente del `Try` bloque o `Catch` en el que aparece. La ejecución continúa con el `Finally` bloque, si hay alguno, o con la instrucción que sigue a la `End Try` instrucción de lo contrario. `Exit Try` solo se puede usar dentro de `Try` un `Catch` bloque o, y no dentro de un `Finally` bloque.

 `Exit While`  
 Sale inmediatamente del `While` bucle en el que aparece. La ejecución continúa con la instrucción que sigue a la `End While` instrucción. `Exit While` solo se puede usar dentro de un `While` bucle. Cuando se usa dentro de `While` bucles anidados, `Exit While` transfiere el control al bucle que está un nivel anidado por encima del bucle en el que `Exit While` se produce.

## <a name="remarks"></a>Observaciones

No confunda `Exit` instrucciones con `End` instrucciones. `Exit` no define el final de una instrucción.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la condición de bucle detiene el bucle cuando la `index` variable es mayor que 100. La `If` instrucción del bucle, sin embargo, hace que la `Exit Do` instrucción detenga el bucle cuando la variable de índice es mayor que 10.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, `Exit Function` se usa para devolver de la función:

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la [instrucción return](return-statement.md) para asignar el valor devuelto y salir de la función:

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>Vea también

- [Continue (instrucción)](continue-statement.md)
- [Instrucción Do...Loop](do-loop-statement.md)
- [End (instrucción)](end-statement.md)
- [Instrucción For Each...Next](for-each-next-statement.md)
- [Instrucción For...Next](for-next-statement.md)
- [Instrucción Function](function-statement.md)
- [Instrucción Return](return-statement.md)
- [Instrucción Stop](stop-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Try...Catch...Finally (instrucción)](try-catch-finally-statement.md)
