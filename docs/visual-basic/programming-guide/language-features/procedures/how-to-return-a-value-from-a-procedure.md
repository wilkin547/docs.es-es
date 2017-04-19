---
title: "Cómo: devolver un valor de un procedimiento (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 98f0fb0740a021a16e87454bfaebbfad7858477c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Cómo: Devolver un valor de un procedimiento (Visual Basic)
Un `Function` procedimiento devuelve un valor al código de llamada ejecutando una `Return` instrucción o encontrando un `Exit Function` o `End Function` instrucción.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Para devolver un valor mediante la instrucción Return  
  
1.  Coloque un `Return` instrucción en el punto donde se ha completado la tarea del procedimiento.  
  
2.  Siga el `Return` palabra clave con una expresión que da como resultado el valor desea volver al código de llamada.  
  
3.  Puede tener más de un `Return` instrucción en el mismo procedimiento.  
  
     La siguiente `Function` procedimiento calcula el lado más largo o la hipotenusa de un triángulo rectángulo y lo devuelve al código de llamada.  
  
     [!code-vb[1 VbVbcnProcedures](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`, que almacena el valor devuelto.  
  
     [!code-vb[VbVbcnProcedures Nº&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Para devolver un valor mediante Exit Function o End Function  
  
1.  En lugar de al menos una de las `Function` procedimiento, asignar un valor para el nombre del procedimiento.  
  
2.  Cuando se ejecuta un `Exit Function` o `End Function` instrucción, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] devuelve el valor asignado más recientemente al nombre del procedimiento.  
  
3.  Puede tener más de un `Exit Function` instrucción en el mismo procedimiento y se puede mezclar `Return` y `Exit Function` las instrucciones en el mismo procedimiento.  
  
4.  Puede tener solo un `End Function` instrucción en un `Function` procedimiento.  
  
     Para obtener más información y un ejemplo, vea "Valor devuelto" en [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Procedimientos de operadores](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return (instrucción)](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [Cómo: crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
