---
description: 'Más información sobre: función CType (Visual Basic)'
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 9732f52b40e5f762769ba5dc340c000e7e1ba17a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701266"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="da38d-103">CType (Función) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da38d-103">CType Function (Visual Basic)</span></span>

<span data-ttu-id="da38d-104">Devuelve el resultado de convertir explícitamente una expresión en un tipo de datos, objeto, estructura, clase o interfaz especificados.</span><span class="sxs-lookup"><span data-stu-id="da38d-104">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="da38d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da38d-105">Syntax</span></span>

```vb
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="da38d-106">Partes</span><span class="sxs-lookup"><span data-stu-id="da38d-106">Parts</span></span>

<span data-ttu-id="da38d-107">`expression` Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="da38d-107">`expression` Any valid expression.</span></span> <span data-ttu-id="da38d-108">Si el valor de `expression` está fuera del intervalo permitido por `typename` , Visual Basic produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="da38d-108">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="da38d-109">`typename` Cualquier expresión válida dentro de una `As` cláusula de una `Dim` instrucción, es decir, el nombre de cualquier tipo de datos, objeto, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="da38d-109">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="da38d-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da38d-110">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="da38d-111">También puede utilizar las siguientes funciones para realizar una conversión de tipos:</span><span class="sxs-lookup"><span data-stu-id="da38d-111">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="da38d-112">Funciones de conversión de tipos como `CByte` , `CDbl` y `CInt` que realizan una conversión a un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="da38d-112">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="da38d-113">Para obtener más información, vea [Funciones de conversión de tipos](type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="da38d-113">For more information, see [Type Conversion Functions](type-conversion-functions.md).</span></span>
> - <span data-ttu-id="da38d-114">[Operador DirectCast](../operators/directcast-operator.md) o [TryCast](../operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="da38d-114">[DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md).</span></span> <span data-ttu-id="da38d-115">Estos operadores requieren que un tipo herede de o implemente el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="da38d-115">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="da38d-116">Pueden proporcionar un rendimiento algo mejor que `CType` al convertir a y desde el `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="da38d-116">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="da38d-117">`CType` está compilado insertado, lo que significa que el código de conversión forma parte del código que evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="da38d-117">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="da38d-118">En algunos casos, el código se ejecuta más rápido porque no se llama a ningún procedimiento para realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="da38d-118">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="da38d-119">Si no se define ninguna conversión de `expression` a `typename` (por ejemplo, de `Integer` a `Date` ), Visual Basic muestra un mensaje de error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="da38d-119">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="da38d-120">Si se produce un error en la conversión en tiempo de ejecución, se produce la excepción adecuada.</span><span class="sxs-lookup"><span data-stu-id="da38d-120">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="da38d-121">Si se produce un error en una conversión de restricción, <xref:System.OverflowException> es el resultado más común.</span><span class="sxs-lookup"><span data-stu-id="da38d-121">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="da38d-122">Si la conversión no está definida, se <xref:System.InvalidCastException> produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="da38d-122">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="da38d-123">Por ejemplo, esto puede ocurrir si `expression` es de tipo `Object` y su tipo en tiempo de ejecución no tiene ninguna conversión a `typename` .</span><span class="sxs-lookup"><span data-stu-id="da38d-123">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="da38d-124">Si el tipo de datos de `expression` o `typename` es una clase o estructura que ha definido, puede definir `CType` en esa clase o estructura como un operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="da38d-124">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="da38d-125">Esto hace `CType` que actúe como un *operador sobrecargado*.</span><span class="sxs-lookup"><span data-stu-id="da38d-125">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="da38d-126">Si lo hace, puede controlar el comportamiento de las conversiones hacia y desde la clase o estructura, incluidas las excepciones que se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="da38d-126">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="da38d-127">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="da38d-127">Overloading</span></span>

<span data-ttu-id="da38d-128">El `CType` operador también se puede sobrecargar en una clase o estructura definida fuera del código.</span><span class="sxs-lookup"><span data-stu-id="da38d-128">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="da38d-129">Si el código se convierte en o desde una clase o estructura de este tipo, asegúrese de que comprende el comportamiento de su `CType` operador.</span><span class="sxs-lookup"><span data-stu-id="da38d-129">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="da38d-130">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="da38d-130">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="da38d-131">Convertir objetos dinámicos</span><span class="sxs-lookup"><span data-stu-id="da38d-131">Converting Dynamic Objects</span></span>

<span data-ttu-id="da38d-132">Las conversiones de tipos de objetos dinámicos se realizan mediante conversiones dinámicas definidas por el usuario que utilizan los <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> métodos o.</span><span class="sxs-lookup"><span data-stu-id="da38d-132">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="da38d-133">Si está trabajando con objetos dinámicos, utilice el <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> método para convertir el objeto dinámico.</span><span class="sxs-lookup"><span data-stu-id="da38d-133">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="da38d-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da38d-134">Example</span></span>

<span data-ttu-id="da38d-135">En el ejemplo siguiente se utiliza la `CType` función para convertir una expresión al `Single` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="da38d-135">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="da38d-136">Para obtener más ejemplos, vea [conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="da38d-136">For additional examples, see [Implicit and Explicit Conversions](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da38d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="da38d-137">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="da38d-138">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="da38d-138">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="da38d-139">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="da38d-139">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="da38d-140">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="da38d-140">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="da38d-141">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="da38d-141">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="da38d-142">Conversión de tipos en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da38d-142">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
