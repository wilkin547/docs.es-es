---
title: La expresión es un valor y, por lo tanto, no puede ser destino de una asignación
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: b2c33cb9ba0479df5e69b6979a789253f9fae565
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597338"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>La expresión es un valor y, por lo tanto, no puede ser destino de una asignación
Una instrucción intenta asignar un valor a una expresión. Puede asignar un valor únicamente a una variable de escritura, propiedad o elemento de matriz en tiempo de ejecución. El ejemplo siguiente muestra cómo puede producirse este error.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Podrían aplicar ejemplos similares a las propiedades y elementos de la matriz.  
  
 **Acceso indirecto.** Acceso indirecto a través de un tipo de valor también puede generar este error. Considere el siguiente ejemplo de código, que intenta establecer el valor de <xref:System.Drawing.Point> accediendo indirectamente a través <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 La última instrucción del ejemplo anterior se produce un error porque crea solo una asignación temporal para la <xref:System.Drawing.Point> estructura devuelta por la <xref:System.Windows.Forms.Control.Location%2A> propiedad. Una estructura es un tipo de valor y la estructura temporal no se conserva después de que se ejecuta la instrucción. El problema se resuelve mediante la declaración y uso de una variable para <xref:System.Windows.Forms.Control.Location%2A>, que crea una asignación más permanente para la <xref:System.Drawing.Point> estructura. El ejemplo siguiente muestra código que puede reemplazar la última instrucción del ejemplo anterior.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Identificador de error:** BC30068  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si la instrucción asigna un valor a una expresión, reemplace la expresión con una variable de escritura única, una propiedad o un elemento de matriz.  
  
-   Si la instrucción obtiene acceso indirecto a través de un tipo de valor (normalmente una estructura), cree una variable que contenga el tipo de valor.  
  
-   Asignar la estructura adecuada (u otro tipo de valor) a la variable.  
  
-   Use la variable para tener acceso a la propiedad para asignarle un valor.  
  
## <a name="see-also"></a>Vea también
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
- [Solución de problemas de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
