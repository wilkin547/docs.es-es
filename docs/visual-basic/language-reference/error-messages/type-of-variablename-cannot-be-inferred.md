---
description: "Más información sobre: BC30982: <variablename> no se puede inferir el tipo de ' ' porque los límites del bucle y la variable Step no se amplían al mismo tipo"
title: No se puede inferir el tipo de '<variablename>' porque los límites del bucle y la variable step no se convierten en el mismo tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 399e021500813127df6ecede2534783df09ac8dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641166"
---
# <a name="bc30982-type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="11740-103">BC30982: \<variablename> no se puede inferir el tipo de ' ' porque los límites del bucle y la variable Step no se amplían al mismo tipo</span><span class="sxs-lookup"><span data-stu-id="11740-103">BC30982: Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="11740-104">Ha escrito un `For...Next` bucle en el que el compilador no puede inferir un tipo de datos para la variable de control de bucle, ya que se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="11740-104">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="11740-105">El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As` .</span><span class="sxs-lookup"><span data-stu-id="11740-105">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="11740-106">Los límites del bucle y la variable step contienen al menos dos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="11740-106">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="11740-107">No existe ninguna conversión estándar entre los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="11740-107">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="11740-108">Por consiguiente, el compilador no puede inferir el tipo de datos de la variable de control de un bucle.</span><span class="sxs-lookup"><span data-stu-id="11740-108">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="11740-109">En el ejemplo siguiente, la variable de paso es un carácter y los límites del bucle son ambos enteros.</span><span class="sxs-lookup"><span data-stu-id="11740-109">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="11740-110">Dado que no hay ninguna conversión estándar entre los caracteres y los enteros, se genera este error.</span><span class="sxs-lookup"><span data-stu-id="11740-110">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="11740-111">**Identificador de error:** BC30982</span><span class="sxs-lookup"><span data-stu-id="11740-111">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="11740-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="11740-112">To correct this error</span></span>

- <span data-ttu-id="11740-113">Cambie los tipos de los límites del bucle y la variable Step según sea necesario para que al menos uno de ellos sea un tipo al que se amplíen los demás.</span><span class="sxs-lookup"><span data-stu-id="11740-113">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="11740-114">En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="11740-114">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="11740-115">o bien</span><span class="sxs-lookup"><span data-stu-id="11740-115">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="11740-116">Use funciones de conversión explícitas para convertir los límites del bucle y la variable de paso en los tipos adecuados.</span><span class="sxs-lookup"><span data-stu-id="11740-116">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="11740-117">En el ejemplo anterior, aplique la `Val` función a `stepVar` .</span><span class="sxs-lookup"><span data-stu-id="11740-117">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="11740-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="11740-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="11740-119">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="11740-119">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="11740-120">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="11740-120">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="11740-121">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="11740-121">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="11740-122">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="11740-122">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="11740-123">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="11740-123">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="11740-124">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="11740-124">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
