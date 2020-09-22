---
title: Las expresiones lambda no son válidas en la primera expresión de una instrucción 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 9f200ea44e7505c407c7df56e596435024394875
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873873"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>Las expresiones lambda no son válidas en la primera expresión de una instrucción 'Select Case'

No se puede usar una expresión lambda para la expresión de prueba en una `Select Case` instrucción. Las definiciones de expresión lambda devuelven funciones y la expresión de prueba de una `Select Case` instrucción debe ser un tipo de datos elemental.  
  
 El código siguiente provoca este error:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Identificador de error:** BC36635  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .  
  
- Es posible que haya previsto llamar a la función, como se muestra en el código siguiente:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Consulte también

- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
- [Instrucción Select...Case](../statements/select-case-statement.md)
