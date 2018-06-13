---
title: '&#39;IsNot&#39; operando de tipo &#39;typename&#39; solo se puede comparar a &#39;nada&#39;, porque &#39;typename&#39; es un tipo que acepta valores null'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587601"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; operando de tipo &#39;typename&#39; solo se puede comparar a &#39;nada&#39;, porque &#39;typename&#39; es un tipo que acepta valores null
Una variable declarada como que acepta valores NULL se ha comparado con una expresión distinta de `Nothing` mediante el `IsNot` operador.  
  
 **Id. de error:** BC32128  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` mediante el uso de la `IsNot` operador, llame a la `GetType` método en el tipo que acepta valores NULL y compare el resultado a la expresión, tal como se muestra en el ejemplo siguiente.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>Vea también  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
