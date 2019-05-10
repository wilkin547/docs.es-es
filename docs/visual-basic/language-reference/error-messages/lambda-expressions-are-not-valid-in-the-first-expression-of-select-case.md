---
title: Las expresiones lambda no son válidas en la primera expresión de una instrucción 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: e9bf248da980705f070be878208c55b0cc6dae01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64589724"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="8b48b-102">Las expresiones lambda no son válidas en la primera expresión de una instrucción 'Select Case'</span><span class="sxs-lookup"><span data-stu-id="8b48b-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>
<span data-ttu-id="8b48b-103">No se puede usar una expresión lambda para la expresión de prueba en un `Select Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8b48b-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="8b48b-104">Definiciones de la expresión lambda que devuelven las funciones y la expresión de prueba de un `Select Case` instrucción debe ser un tipo de datos básico.</span><span class="sxs-lookup"><span data-stu-id="8b48b-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="8b48b-105">El código siguiente provoca este error:</span><span class="sxs-lookup"><span data-stu-id="8b48b-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="8b48b-106">**Identificador de error:** BC36635</span><span class="sxs-lookup"><span data-stu-id="8b48b-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8b48b-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8b48b-107">To correct this error</span></span>  
  
- <span data-ttu-id="8b48b-108">Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="8b48b-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
- <span data-ttu-id="8b48b-109">Puede haber pensado llamar a la función, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="8b48b-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b48b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b48b-110">See also</span></span>

- [<span data-ttu-id="8b48b-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="8b48b-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="8b48b-112">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b48b-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="8b48b-113">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b48b-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
