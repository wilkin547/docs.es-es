---
title: "Tipo de &#39; &lt;variablename&gt;&#39; no se puede inferir porque los límites del bucle y la variable step no se convierten en el mismo tipo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords: BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="14684-102">Tipo de &#39; &lt;variablename&gt;&#39; no se puede inferir porque los límites del bucle y la variable step no se convierten en el mismo tipo</span><span class="sxs-lookup"><span data-stu-id="14684-102">Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="14684-103">Ha escrito un `For...Next` bucle en el que el compilador no puede inferir un tipo de datos para la variable de control de bucle porque las condiciones siguientes son ciertas:</span><span class="sxs-lookup"><span data-stu-id="14684-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="14684-104">El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As` .</span><span class="sxs-lookup"><span data-stu-id="14684-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="14684-105">Los límites del bucle y la variable step contienen al menos dos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="14684-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="14684-106">No existe ninguna conversión estándar entre los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="14684-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="14684-107">Por lo tanto, el compilador no puede inferir el tipo de datos de la variable de control del bucle.</span><span class="sxs-lookup"><span data-stu-id="14684-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="14684-108">En el ejemplo siguiente, la variable step es un carácter y los límites del bucle son dos enteros.</span><span class="sxs-lookup"><span data-stu-id="14684-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="14684-109">Porque no hay ninguna conversión estándar entre caracteres y números enteros, se informa de este error.</span><span class="sxs-lookup"><span data-stu-id="14684-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="14684-110">**Id. de error:** BC30982</span><span class="sxs-lookup"><span data-stu-id="14684-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14684-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="14684-111">To correct this error</span></span>  
  
-   <span data-ttu-id="14684-112">Cambiar los tipos de los límites del bucle y la variable step según sea necesario para que al menos uno de ellos es un tipo que amplían los demás.</span><span class="sxs-lookup"><span data-stu-id="14684-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="14684-113">En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="14684-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="14684-114">-O bien-</span><span class="sxs-lookup"><span data-stu-id="14684-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="14684-115">Usar funciones de conversión explícita para convertir los límites del bucle y la variable step a los tipos adecuados.</span><span class="sxs-lookup"><span data-stu-id="14684-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="14684-116">En el ejemplo anterior, se aplica el `Val` función `stepVar`.</span><span class="sxs-lookup"><span data-stu-id="14684-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="14684-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="14684-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="14684-118">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="14684-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="14684-119">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="14684-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="14684-120">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="14684-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="14684-121">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="14684-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="14684-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="14684-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="14684-123">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="14684-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
