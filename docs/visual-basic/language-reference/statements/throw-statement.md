---
title: Throw (Instrucción, Visual Basic)
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
ms.openlocfilehash: a6d10982cf199e9285334e0d72e6622275d51b4d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626196"
---
# <a name="throw-statement-visual-basic"></a>Throw (Instrucción, Visual Basic)
Produce una excepción dentro de un procedimiento.

## <a name="syntax"></a>Sintaxis

```vb
Throw [ expression ]
```

## <a name="part"></a>Parte
 `expression`Proporciona información sobre la excepción que se va a producir. Opcional cuando reside en una `Catch` instrucción; de lo contrario, es obligatorio.
  
## <a name="remarks"></a>Comentarios
 La `Throw` instrucción produce una excepción que se puede controlar con código estructurado de control de excepciones (`Try`... `Catch`... ) o el código de control de excepciones no estructurado`On Error GoTo`(). `Finally` Puede usar la `Throw` instrucción para interceptar errores dentro del código porque Visual Basic sube la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.
 
 Una `Throw` instrucción sin expresión solo se puede usar en una `Catch` instrucción, en cuyo caso la instrucción vuelve a iniciar la excepción que está controlando actualmente la `Catch` instrucción.

 La `Throw` instrucción restablece la pila de llamadas de la `expression` excepción. Si `expression` no se proporciona, la pila de llamadas permanece sin cambios. Puede tener acceso a la pila de llamadas de la excepción <xref:System.Exception.StackTrace%2A> a través de la propiedad.

## <a name="example"></a>Ejemplo
 En el código siguiente se `Throw` usa la instrucción para producir una excepción:
 
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

  
## <a name="see-also"></a>Vea también

- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
