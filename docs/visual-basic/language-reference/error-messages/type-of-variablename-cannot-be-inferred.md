---
title: No se puede inferir el tipo de '<variablename>' porque los límites del bucle y la variable step no se convierten en el mismo tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 1330cbd6567b69df9bd811ced49c6df2e120a0b2
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161214"
---
# <a name="bc30982-type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="d10fe-102">BC30982: \<variablename> no se puede inferir el tipo de ' ' porque los límites del bucle y la variable Step no se amplían al mismo tipo</span><span class="sxs-lookup"><span data-stu-id="d10fe-102">BC30982: Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="d10fe-103">Ha escrito un `For...Next` bucle en el que el compilador no puede inferir un tipo de datos para la variable de control de bucle, ya que se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d10fe-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="d10fe-104">El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As` .</span><span class="sxs-lookup"><span data-stu-id="d10fe-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="d10fe-105">Los límites del bucle y la variable step contienen al menos dos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="d10fe-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="d10fe-106">No existe ninguna conversión estándar entre los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="d10fe-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="d10fe-107">Por consiguiente, el compilador no puede inferir el tipo de datos de la variable de control de un bucle.</span><span class="sxs-lookup"><span data-stu-id="d10fe-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="d10fe-108">En el ejemplo siguiente, la variable de paso es un carácter y los límites del bucle son ambos enteros.</span><span class="sxs-lookup"><span data-stu-id="d10fe-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="d10fe-109">Dado que no hay ninguna conversión estándar entre los caracteres y los enteros, se genera este error.</span><span class="sxs-lookup"><span data-stu-id="d10fe-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="d10fe-110">**Identificador de error:** BC30982</span><span class="sxs-lookup"><span data-stu-id="d10fe-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d10fe-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d10fe-111">To correct this error</span></span>

- <span data-ttu-id="d10fe-112">Cambie los tipos de los límites del bucle y la variable Step según sea necesario para que al menos uno de ellos sea un tipo al que se amplíen los demás.</span><span class="sxs-lookup"><span data-stu-id="d10fe-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="d10fe-113">En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="d10fe-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="d10fe-114">o bien</span><span class="sxs-lookup"><span data-stu-id="d10fe-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="d10fe-115">Use funciones de conversión explícitas para convertir los límites del bucle y la variable de paso en los tipos adecuados.</span><span class="sxs-lookup"><span data-stu-id="d10fe-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="d10fe-116">En el ejemplo anterior, aplique la `Val` función a `stepVar` .</span><span class="sxs-lookup"><span data-stu-id="d10fe-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="d10fe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d10fe-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="d10fe-118">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="d10fe-118">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="d10fe-119">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="d10fe-119">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="d10fe-120">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="d10fe-120">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d10fe-121">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d10fe-121">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="d10fe-122">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="d10fe-122">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="d10fe-123">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="d10fe-123">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
