---
title: Las expresiones lambda no son válidas en la primera expresión de un &#39;Select Case&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: afefa821f9695dbbfe2a96aee5afd3171ae5b1db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700226"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Las expresiones lambda no son válidas en la primera expresión de un &#39;Select Case&#39; instrucción
No se puede usar una expresión lambda para la expresión de prueba en un `Select Case` instrucción. Definiciones de la expresión lambda que devuelven las funciones y la expresión de prueba de un `Select Case` instrucción debe ser un tipo de datos básico.  
  
 El código siguiente provoca este error:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Identificador de error:** BC36635  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .  
  
-   Puede haber pensado llamar a la función, tal como se muestra en el código siguiente:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Vea también
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case (instrucción)](../../../visual-basic/language-reference/statements/select-case-statement.md)
