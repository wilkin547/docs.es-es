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
ms.openlocfilehash: 2494eac2f61f112f3ba6321ada7404f8cd618049
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821397"
---
# <a name="throw-statement-visual-basic"></a>Throw (Instrucción, Visual Basic)
Se produce una excepción dentro de un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Proporciona información sobre la excepción que se produzca. Opcional si se encuentra en un `Catch` instrucción, de lo contrario requerido.  
  
## <a name="remarks"></a>Comentarios  
 El `Throw` instrucción produce una excepción que se puede controlar con código de control de excepciones estructurado (`Try`... `Catch`... `Finally`) o el código de control de excepciones no estructurado (`On Error GoTo`). Puede usar el `Throw` instrucción para interceptar errores dentro del código porque Visual Basic asciende por la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.  
  
 Un `Throw` instrucción sin una expresión solo se puede usar en un `Catch` instrucción, en el que la instrucción case, vuelve a producir la excepción que se controla actualmente por el `Catch` instrucción.  
  
 El `Throw` instrucción restablece la pila de llamadas para el `expression` excepción. Si `expression` no se proporciona, la pila de llamadas permanece inalterado. Puede tener acceso a la pila de llamadas para la excepción a través de la <xref:System.Exception.StackTrace%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código utiliza el `Throw` instrucción para producir una excepción:  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:** `Interaction`  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también

- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
