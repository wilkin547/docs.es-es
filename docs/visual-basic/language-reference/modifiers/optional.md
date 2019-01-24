---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 7db5f8afdfe61709aba9569bcee8c0d3aa6ee44f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527047"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="35adf-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35adf-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="35adf-103">Especifica que se puede omitir un argumento de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35adf-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35adf-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35adf-104">Remarks</span></span>  
 <span data-ttu-id="35adf-105">Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="35adf-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="35adf-106">Si la expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el valor predeterminado del tipo de datos de valor se utiliza como el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="35adf-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="35adf-107">Si la lista de parámetros contiene un parámetro opcional, también deben ser opcional todos los parámetros que le sigue.</span><span class="sxs-lookup"><span data-stu-id="35adf-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="35adf-108">El modificador `Optional` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="35adf-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="35adf-109">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="35adf-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="35adf-110">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="35adf-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="35adf-111">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="35adf-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="35adf-112">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="35adf-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="35adf-113">Al llamar a un procedimiento con o sin parámetros opcionales, puede pasar argumentos por posición o por nombre.</span><span class="sxs-lookup"><span data-stu-id="35adf-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="35adf-114">Para obtener más información, consulte [pasar argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="35adf-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35adf-115">También puede definir un procedimiento con parámetros opcionales mediante la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="35adf-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="35adf-116">Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, uno que acepta el parámetro y uno que no lo hace.</span><span class="sxs-lookup"><span data-stu-id="35adf-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="35adf-117">Para obtener más información, consulta [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="35adf-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35adf-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35adf-118">Example</span></span>  
 <span data-ttu-id="35adf-119">El ejemplo siguiente define un procedimiento que tiene un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="35adf-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="35adf-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35adf-120">Example</span></span>  
 <span data-ttu-id="35adf-121">El ejemplo siguiente muestra cómo llamar a un procedimiento con los argumentos pasados por posición y con los argumentos pasados por nombre.</span><span class="sxs-lookup"><span data-stu-id="35adf-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="35adf-122">El procedimiento tiene dos parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="35adf-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="35adf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="35adf-123">See also</span></span>
- [<span data-ttu-id="35adf-124">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="35adf-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="35adf-125">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="35adf-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="35adf-126">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="35adf-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
