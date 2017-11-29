---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Especifica que se puede omitir un argumento de procedimiento cuando se llama al procedimiento.  
  
## <a name="remarks"></a>Comentarios  
 Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro. Si la expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el valor predeterminado del tipo de datos de valor se utiliza como el valor predeterminado del parámetro.  
  
 Si la lista de parámetros contiene un parámetro opcional, todos los parámetros que hay a continuación también deben ser opcional.  
  
 El modificador `Optional` se puede utilizar en los contextos siguientes:  
  
-   [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Al llamar a un procedimiento con o sin parámetros opcionales, puede pasar argumentos por posición o por nombre. Para obtener más información, consulte [pasar argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  También puede definir un procedimiento con parámetros opcionales mediante el uso de sobrecarga. Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepta el parámetro y uno que no. Para obtener más información, consulte [sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un procedimiento que tiene un parámetro opcional.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar a un procedimiento con argumentos pasados por posición y con los argumentos pasados por nombre. El procedimiento tiene dos parámetros opcionales.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
