---
title: Las expresiones lambda no son válidas en la primera expresión de una &#39;Select Case&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: c492615850ec089fe35c1ae4eaba90a741e30f42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Las expresiones lambda no son válidas en la primera expresión de una &#39;Select Case&#39; instrucción
No se puede usar una expresión lambda para la expresión de prueba en un `Select Case` instrucción. Definiciones de la expresión lambda devuelven funciones y la expresión de prueba de un `Select Case` instrucción debe ser un tipo de datos básico.  
  
 El código siguiente provoca este error:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Id. de error:** BC36635  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .  
  
-   Puede haber pensado llamar a la función, como se muestra en el código siguiente:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Vea también  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Select...Case (instrucción)](../../../visual-basic/language-reference/statements/select-case-statement.md)
