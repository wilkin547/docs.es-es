---
title: El operando 'IsNot' de tipo 'nombreDeTipo' solo se puede comparar con 'Nothing', porque 'nombreDeTipo' es un tipo que acepta valores NULL
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: f19b8cd5f80ba9fd6d1f5a9162b04ee409e24e28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921139"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="61df9-102">El operando 'IsNot' de tipo 'nombreDeTipo' solo se puede comparar con 'Nothing', porque 'nombreDeTipo' es un tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="61df9-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>
<span data-ttu-id="61df9-103">Una variable declarada como que acepta valores NULL se ha comparado con una expresión distinta `Nothing` utilizando el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="61df9-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="61df9-104">**Identificador de error:** BC32128</span><span class="sxs-lookup"><span data-stu-id="61df9-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61df9-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="61df9-105">To correct this error</span></span>  
  
1. <span data-ttu-id="61df9-106">Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` con el operador `IsNot` , llame al método `GetType` en el tipo que acepta valores NULL y compare el resultado con la expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="61df9-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="61df9-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="61df9-107">See also</span></span>

- [<span data-ttu-id="61df9-108">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="61df9-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="61df9-109">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="61df9-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
