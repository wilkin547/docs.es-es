---
title: Operador DirectCast
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 7b070b8eba240440821f7984a9336c2ecaf61706
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867091"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="2c56c-102">DirectCast (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c56c-102">DirectCast Operator (Visual Basic)</span></span>

<span data-ttu-id="2c56c-103">Introduce una operación de conversión de tipos basada en la herencia o la implementación.</span><span class="sxs-lookup"><span data-stu-id="2c56c-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c56c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c56c-104">Remarks</span></span>  

 <span data-ttu-id="2c56c-105">`DirectCast` no utiliza las rutinas auxiliares en tiempo de ejecución de Visual Basic para la conversión, por lo que puede proporcionar un rendimiento algo mejor que `CType` al convertir a y desde el tipo de datos `Object` .</span><span class="sxs-lookup"><span data-stu-id="2c56c-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="2c56c-106">La palabra clave se usa de `DirectCast` manera similar a la forma en que se usa la [función ctype](../functions/ctype-function.md) y la palabra clave del [operador TryCast](trycast-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="2c56c-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../functions/ctype-function.md) and the [TryCast Operator](trycast-operator.md) keyword.</span></span> <span data-ttu-id="2c56c-107">Proporcione una expresión como primer argumento y un tipo al que convertirlo como segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="2c56c-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="2c56c-108">`DirectCast` requiere una relación de herencia o implementación entre los tipos de datos de los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="2c56c-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="2c56c-109">Esto significa que un tipo debe heredar de o implementar el otro.</span><span class="sxs-lookup"><span data-stu-id="2c56c-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="2c56c-110">Errores y errores</span><span class="sxs-lookup"><span data-stu-id="2c56c-110">Errors and Failures</span></span>  

 <span data-ttu-id="2c56c-111">`DirectCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o de implementación.</span><span class="sxs-lookup"><span data-stu-id="2c56c-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="2c56c-112">Pero la falta de un error del compilador no garantiza una conversión correcta.</span><span class="sxs-lookup"><span data-stu-id="2c56c-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="2c56c-113">Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c56c-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="2c56c-114">Si esto ocurre, el tiempo de ejecución produce un <xref:System.InvalidCastException> error.</span><span class="sxs-lookup"><span data-stu-id="2c56c-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="2c56c-115">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="2c56c-115">Conversion Keywords</span></span>  

 <span data-ttu-id="2c56c-116">A continuación se muestra una comparación de las palabras clave de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="2c56c-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="2c56c-117">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="2c56c-117">Keyword</span></span>|<span data-ttu-id="2c56c-118">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="2c56c-118">Data types</span></span>|<span data-ttu-id="2c56c-119">Relación entre argumentos</span><span class="sxs-lookup"><span data-stu-id="2c56c-119">Argument relationship</span></span>|<span data-ttu-id="2c56c-120">Error en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2c56c-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="2c56c-121">CType Function</span><span class="sxs-lookup"><span data-stu-id="2c56c-121">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="2c56c-122">Cualquier tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2c56c-122">Any data types</span></span>|<span data-ttu-id="2c56c-123">La conversión de ampliación o de restricción debe definirse entre los dos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="2c56c-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="2c56c-124">Produce <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="2c56c-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="2c56c-125">Cualquier tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2c56c-125">Any data types</span></span>|<span data-ttu-id="2c56c-126">Un tipo debe heredar de o implementar el otro tipo</span><span class="sxs-lookup"><span data-stu-id="2c56c-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="2c56c-127">Produce <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="2c56c-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="2c56c-128">Operador TryCast</span><span class="sxs-lookup"><span data-stu-id="2c56c-128">TryCast Operator</span></span>](trycast-operator.md)|<span data-ttu-id="2c56c-129">Solo tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="2c56c-129">Reference types only</span></span>|<span data-ttu-id="2c56c-130">Un tipo debe heredar de o implementar el otro tipo</span><span class="sxs-lookup"><span data-stu-id="2c56c-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="2c56c-131">No devuelve [nada](../nothing.md)</span><span class="sxs-lookup"><span data-stu-id="2c56c-131">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2c56c-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c56c-132">Example</span></span>  

 <span data-ttu-id="2c56c-133">En el ejemplo siguiente se muestran dos usos de `DirectCast` , uno que produce un error en tiempo de ejecución y otro que se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c56c-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="2c56c-134">En el ejemplo anterior, el tipo en tiempo de ejecución de `q` es `Double` .</span><span class="sxs-lookup"><span data-stu-id="2c56c-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="2c56c-135">`CType` se realiza correctamente porque `Double` se puede convertir en `Integer` .</span><span class="sxs-lookup"><span data-stu-id="2c56c-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="2c56c-136">Sin embargo, el primer `DirectCast` error en el tiempo de ejecución porque el tipo en tiempo de ejecución de `Double` no tiene ninguna relación de herencia con `Integer` , aunque exista una conversión.</span><span class="sxs-lookup"><span data-stu-id="2c56c-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="2c56c-137">La segunda operación `DirectCast` se realiza correctamente porque convierte de tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control> , desde el que <xref:System.Windows.Forms.Form> hereda.</span><span class="sxs-lookup"><span data-stu-id="2c56c-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c56c-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c56c-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2c56c-139">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="2c56c-139">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="2c56c-140">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="2c56c-140">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
