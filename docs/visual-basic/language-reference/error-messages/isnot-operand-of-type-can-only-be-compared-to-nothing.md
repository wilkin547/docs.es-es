---
title: '&#39;IsNot&#39; operando de tipo &#39;typename&#39; solo puede compararse con &#39;nada&#39;, porque &#39;typename&#39; es un tipo que acepta valores null'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505723"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; operando de tipo &#39;typename&#39; solo puede compararse con &#39;nada&#39;, porque &#39;typename&#39; es un tipo que acepta valores null
Una variable declarada como que acepta valores NULL se ha comparado con una expresión distinta `Nothing` utilizando el `IsNot` operador.  
  
 **Identificador de error:** BC32128  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` con el operador `IsNot` , llame al método `GetType` en el tipo que acepta valores NULL y compare el resultado con la expresión, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>Vea también
- [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
