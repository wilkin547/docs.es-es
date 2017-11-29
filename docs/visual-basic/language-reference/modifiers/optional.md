---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a><span data-ttu-id="e81dd-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e81dd-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="e81dd-103">Especifica que se puede omitir un argumento de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e81dd-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e81dd-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e81dd-104">Remarks</span></span>  
 <span data-ttu-id="e81dd-105">Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="e81dd-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="e81dd-106">Si la expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el valor predeterminado del tipo de datos de valor se utiliza como el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="e81dd-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="e81dd-107">Si la lista de parámetros contiene un parámetro opcional, todos los parámetros que hay a continuación también deben ser opcional.</span><span class="sxs-lookup"><span data-stu-id="e81dd-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="e81dd-108">El modificador `Optional` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e81dd-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="e81dd-109">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e81dd-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="e81dd-110">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e81dd-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="e81dd-111">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e81dd-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="e81dd-112">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e81dd-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="e81dd-113">Al llamar a un procedimiento con o sin parámetros opcionales, puede pasar argumentos por posición o por nombre.</span><span class="sxs-lookup"><span data-stu-id="e81dd-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="e81dd-114">Para obtener más información, consulte [pasar argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="e81dd-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e81dd-115">También puede definir un procedimiento con parámetros opcionales mediante el uso de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="e81dd-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="e81dd-116">Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepta el parámetro y uno que no.</span><span class="sxs-lookup"><span data-stu-id="e81dd-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="e81dd-117">Para obtener más información, consulte [sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="e81dd-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e81dd-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e81dd-118">Example</span></span>  
 <span data-ttu-id="e81dd-119">En el ejemplo siguiente se define un procedimiento que tiene un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="e81dd-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="e81dd-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e81dd-120">Example</span></span>  
 <span data-ttu-id="e81dd-121">En el ejemplo siguiente se muestra cómo llamar a un procedimiento con argumentos pasados por posición y con los argumentos pasados por nombre.</span><span class="sxs-lookup"><span data-stu-id="e81dd-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="e81dd-122">El procedimiento tiene dos parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="e81dd-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e81dd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e81dd-123">See Also</span></span>  
 [<span data-ttu-id="e81dd-124">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="e81dd-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="e81dd-125">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="e81dd-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="e81dd-126">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e81dd-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
