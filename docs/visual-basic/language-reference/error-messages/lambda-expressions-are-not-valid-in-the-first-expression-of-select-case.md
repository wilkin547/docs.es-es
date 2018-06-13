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
ms.locfileid: "33588926"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="a8637-102">Las expresiones lambda no son válidas en la primera expresión de una &#39;Select Case&#39; instrucción</span><span class="sxs-lookup"><span data-stu-id="a8637-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="a8637-103">No se puede usar una expresión lambda para la expresión de prueba en un `Select Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a8637-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="a8637-104">Definiciones de la expresión lambda devuelven funciones y la expresión de prueba de un `Select Case` instrucción debe ser un tipo de datos básico.</span><span class="sxs-lookup"><span data-stu-id="a8637-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="a8637-105">El código siguiente provoca este error:</span><span class="sxs-lookup"><span data-stu-id="a8637-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="a8637-106">**Id. de error:** BC36635</span><span class="sxs-lookup"><span data-stu-id="a8637-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8637-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a8637-107">To correct this error</span></span>  
  
-   <span data-ttu-id="a8637-108">Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="a8637-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="a8637-109">Puede haber pensado llamar a la función, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8637-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8637-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8637-110">See Also</span></span>  
 [<span data-ttu-id="a8637-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="a8637-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="a8637-112">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a8637-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="a8637-113">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a8637-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
