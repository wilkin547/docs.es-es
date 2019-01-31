---
title: No se puede inferir el tipo de '<variablename>' porque los límites del bucle y la variable step no se convierten en el mismo tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 1f1df0c7391c027994caabadc4b857bec55f5938
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287502"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="33645-102">Tipo de '\<NombreDeVariable >' no se puede inferir porque los límites del bucle y la variable step no se convierten en el mismo tipo</span><span class="sxs-lookup"><span data-stu-id="33645-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="33645-103">Ha escrito un `For...Next` bucle en el que el compilador no puede inferir un tipo de datos para la variable de control de bucle porque se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="33645-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="33645-104">El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As` .</span><span class="sxs-lookup"><span data-stu-id="33645-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="33645-105">Los límites del bucle y la variable step contienen al menos dos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="33645-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="33645-106">No existe ninguna conversión estándar entre los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="33645-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="33645-107">Por lo tanto, el compilador no puede inferir el tipo de datos de variable de control de un bucle.</span><span class="sxs-lookup"><span data-stu-id="33645-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="33645-108">En el ejemplo siguiente, la variable step es un carácter y los límites del bucle son dos enteros.</span><span class="sxs-lookup"><span data-stu-id="33645-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="33645-109">Dado que no hay ninguna conversión estándar entre caracteres y números enteros, se notifica este error.</span><span class="sxs-lookup"><span data-stu-id="33645-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="33645-110">**Identificador de error:** BC30982</span><span class="sxs-lookup"><span data-stu-id="33645-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33645-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="33645-111">To correct this error</span></span>  
  
-   <span data-ttu-id="33645-112">Cambiar los tipos de los límites del bucle y la variable step según sea necesario para que al menos uno de ellos es un tipo que amplían los demás.</span><span class="sxs-lookup"><span data-stu-id="33645-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="33645-113">En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="33645-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="33645-114">-O bien-</span><span class="sxs-lookup"><span data-stu-id="33645-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="33645-115">Usar funciones de conversión explícita para convertir los límites del bucle y la variable step a los tipos adecuados.</span><span class="sxs-lookup"><span data-stu-id="33645-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="33645-116">En el ejemplo anterior, se aplican los `Val` función `stepVar`.</span><span class="sxs-lookup"><span data-stu-id="33645-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33645-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="33645-117">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="33645-118">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="33645-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="33645-119">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="33645-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="33645-120">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="33645-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="33645-121">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="33645-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="33645-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="33645-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="33645-123">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="33645-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
