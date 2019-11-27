---
title: Throw (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352789"
---
# <a name="throw-statement-visual-basic"></a>Throw (Instrucción, Visual Basic)

Produce una excepción dentro de un procedimiento.

## <a name="syntax"></a>Sintaxis

```vb
Throw [ expression ]
```

## <a name="part"></a>Parte

`expression`\
Proporciona información sobre la excepción que se va a producir. Opcional cuando reside en una instrucción `Catch`, si es necesario.

## <a name="remarks"></a>Comentarios

La instrucción `Throw` produce una excepción que se puede controlar con el código estructurado de control de excepciones (`Try`...`Catch`...`Finally`) o el código de control de excepciones no estructurado (`On Error GoTo`). Puede utilizar la instrucción `Throw` para interceptar los errores dentro del código porque Visual Basic sube por la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.

Una instrucción `Throw` sin expresión solo se puede usar en una instrucción `Catch`, en cuyo caso la instrucción vuelve a producir la excepción que controla actualmente la instrucción `Catch`.

La instrucción `Throw` restablece la pila de llamadas de la excepción `expression`. Si no se proporciona `expression`, la pila de llamadas permanece sin cambios. Puede tener acceso a la pila de llamadas de la excepción a través de la propiedad <xref:System.Exception.StackTrace%2A>.

## <a name="example"></a>Ejemplo

En el código siguiente se usa la instrucción `Throw` para producir una excepción:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>Vea también

- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
