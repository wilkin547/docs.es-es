---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 40605d4843bfccf9d2819b3ec6f2ef65f9e9cf9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661326"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Especifica que se puede omitir un argumento de procedimiento cuando se llama al procedimiento.  
  
## <a name="remarks"></a>Comentarios  
 Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro. Si la expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el valor predeterminado del tipo de datos de valor se utiliza como el valor predeterminado del parámetro.  
  
 Si la lista de parámetros contiene un parámetro opcional, también deben ser opcional todos los parámetros que le sigue.  
  
 El modificador `Optional` se puede utilizar en los contextos siguientes:  
  
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Al llamar a un procedimiento con o sin parámetros opcionales, puede pasar argumentos por posición o por nombre. Para obtener más información, consulte [pasar argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  También puede definir un procedimiento con parámetros opcionales mediante la sobrecarga. Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, uno que acepta el parámetro y uno que no lo hace. Para obtener más información, consulta [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente define un procedimiento que tiene un parámetro opcional.  
  
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
 El ejemplo siguiente muestra cómo llamar a un procedimiento con los argumentos pasados por posición y con los argumentos pasados por nombre. El procedimiento tiene dos parámetros opcionales.  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a>Vea también

- [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
