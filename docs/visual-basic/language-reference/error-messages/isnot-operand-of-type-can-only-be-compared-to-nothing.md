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
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="69d8f-102">&#39;IsNot&#39; operando de tipo &#39;typename&#39; solo puede compararse con &#39;nada&#39;, porque &#39;typename&#39; es un tipo que acepta valores null</span><span class="sxs-lookup"><span data-stu-id="69d8f-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="69d8f-103">Una variable declarada como que acepta valores NULL se ha comparado con una expresión distinta `Nothing` utilizando el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="69d8f-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="69d8f-104">**Identificador de error:** BC32128</span><span class="sxs-lookup"><span data-stu-id="69d8f-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69d8f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="69d8f-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="69d8f-106">Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` con el operador `IsNot` , llame al método `GetType` en el tipo que acepta valores NULL y compare el resultado con la expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="69d8f-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="69d8f-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="69d8f-107">See also</span></span>
- [<span data-ttu-id="69d8f-108">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="69d8f-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="69d8f-109">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="69d8f-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
