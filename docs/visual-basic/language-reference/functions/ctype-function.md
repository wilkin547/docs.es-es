---
title: "CType (Función) (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6118ca5f73a0d446842c33859e0623032082bcd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="96053-102">CType (Función) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96053-102">CType Function (Visual Basic)</span></span>
<span data-ttu-id="96053-103">Devuelve el resultado de convertir explícitamente una expresión a una estructura, clase, tipo de datos especificado, objeto o interfaz.</span><span class="sxs-lookup"><span data-stu-id="96053-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96053-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96053-104">Syntax</span></span>  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a><span data-ttu-id="96053-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="96053-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="96053-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="96053-106">Any valid expression.</span></span> <span data-ttu-id="96053-107">Si el valor de `expression` está fuera del intervalo permitido por `typename`, Visual Basic produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="96053-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>  
  
 `typename`  
 <span data-ttu-id="96053-108">Cualquier expresión válida dentro de un `As` cláusula en una `Dim` instrucción, es decir, el nombre de cualquier tipo de datos objeto, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="96053-108">Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96053-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96053-109">Remarks</span></span>  
  
> [!TIP]
>  <span data-ttu-id="96053-110">También puede utilizar las siguientes funciones para realizar una conversión de tipos:</span><span class="sxs-lookup"><span data-stu-id="96053-110">You can also use the following functions to perform a type conversion:</span></span>  
>   
>  -   <span data-ttu-id="96053-111">Escriba las funciones de conversión como `CByte`, `CDbl`, y `CInt` que realizar una conversión a un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="96053-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="96053-112">Para obtener más información, consulte [funciones de conversión de tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="96053-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
> -   <span data-ttu-id="96053-113">[DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="96053-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="96053-114">Estos operadores requieren que hereda de un tipo ni lo implementa el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="96053-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="96053-115">Puede proporcionar un mejor rendimiento que `CType` al convertir a y desde el `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="96053-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>  
  
 <span data-ttu-id="96053-116">`CType`está compilado en línea, lo que significa que el código de conversión forma parte del código que evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="96053-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="96053-117">En algunos casos, el código se ejecuta con mayor rapidez porque no se llama a ningún procedimiento para realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="96053-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>  
  
 <span data-ttu-id="96053-118">Si no se ha definido ninguna conversión de `expression` a `typename` (por ejemplo, de `Integer` a `Date`), Visual Basic muestra un mensaje de error de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="96053-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>  
  
 <span data-ttu-id="96053-119">Si se produce un error en una conversión en tiempo de ejecución, se produce la excepción adecuada.</span><span class="sxs-lookup"><span data-stu-id="96053-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="96053-120">Si se produce un error en una conversión de restricción, un <xref:System.OverflowException> es el resultado más comunes.</span><span class="sxs-lookup"><span data-stu-id="96053-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="96053-121">Si la conversión no está definida, un <xref:System.InvalidCastException> en produce.</span><span class="sxs-lookup"><span data-stu-id="96053-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="96053-122">Por ejemplo, esto puede suceder si `expression` es de tipo `Object` y su tipo en tiempo de ejecución no tiene ninguna conversión a `typename`.</span><span class="sxs-lookup"><span data-stu-id="96053-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>  
  
 <span data-ttu-id="96053-123">Si el tipo de datos de `expression` o `typename` es una clase o estructura que ha definido, puede definir `CType` en esa clase o estructura como un operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="96053-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="96053-124">Esto hace que `CType` actúan como un *operador sobrecargado*.</span><span class="sxs-lookup"><span data-stu-id="96053-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="96053-125">Si lo hace, puede controlar el comportamiento de las conversiones a y desde la clase o estructura, incluidas las excepciones que se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="96053-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="96053-126">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="96053-126">Overloading</span></span>  
 <span data-ttu-id="96053-127">El `CType` también se puede sobrecargar el operador en una clase o estructura definida fuera del código.</span><span class="sxs-lookup"><span data-stu-id="96053-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="96053-128">Si el código se convierte a o desde una clase o estructura de este tipo, asegúrese de que comprende el comportamiento de su `CType` operador.</span><span class="sxs-lookup"><span data-stu-id="96053-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="96053-129">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="96053-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="converting-dynamic-objects"></a><span data-ttu-id="96053-130">Convertir objetos dinámicos</span><span class="sxs-lookup"><span data-stu-id="96053-130">Converting Dynamic Objects</span></span>  
 <span data-ttu-id="96053-131">Conversiones de tipos de objetos dinámicos realiza las conversiones dinámicas definidas por el usuario que utilizan el <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="96053-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="96053-132">Si está trabajando con objetos dinámicos, use la <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> método para convertir el objeto dinámico.</span><span class="sxs-lookup"><span data-stu-id="96053-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96053-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96053-133">Example</span></span>  
 <span data-ttu-id="96053-134">En el ejemplo siguiente se usa el `CType` función para convertir una expresión a la `Single` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="96053-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 <span data-ttu-id="96053-135">Para obtener ejemplos adicionales, vea [conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="96053-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96053-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="96053-136">See Also</span></span>  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="96053-137">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="96053-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="96053-138">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="96053-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="96053-139">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96053-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="96053-140">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="96053-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="96053-141">Conversión de tipos en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="96053-141">Type Conversion in the .NET Framework</span></span>](http://msdn.microsoft.com/library/ba36154f-064c-47d3-9f05-72f93a7ca96d)
