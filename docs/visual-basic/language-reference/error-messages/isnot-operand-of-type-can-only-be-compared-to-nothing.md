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
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="4e7fe-102">&#39;IsNot&#39; operando de tipo &#39;typename&#39; solo se puede comparar a &#39;nada&#39;, porque &#39;typename&#39; es un tipo que acepta valores null</span><span class="sxs-lookup"><span data-stu-id="4e7fe-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="4e7fe-103">Una variable declarada como que acepta valores NULL se ha comparado con una expresión distinta de `Nothing` mediante el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="4e7fe-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="4e7fe-104">**Id. de error:** BC32128</span><span class="sxs-lookup"><span data-stu-id="4e7fe-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e7fe-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4e7fe-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="4e7fe-106">Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` mediante el uso de la `IsNot` operador, llame a la `GetType` método en el tipo que acepta valores NULL y compare el resultado a la expresión, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4e7fe-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e7fe-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e7fe-107">See Also</span></span>  
 [<span data-ttu-id="4e7fe-108">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="4e7fe-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="4e7fe-109">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="4e7fe-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
