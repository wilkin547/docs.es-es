---
title: 'Conversión boxing y unboxing: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 62df08bf4ae3580e9b8d5b3aab0697d396674ca1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745415"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="ec981-102">Conversión boxing y unboxing (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ec981-102">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="ec981-103">La conversión boxing es el proceso de convertir un [tipo de valor](../../language-reference/builtin-types/value-types.md) en el tipo `object` o en cualquier tipo de interfaz implementado por este tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ec981-103">Boxing is the process of converting a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="ec981-104">Cuando Common Language Runtime (CLR) aplica la conversión boxing a un tipo de valor, ajusta el valor dentro de una instancia <xref:System.Object?displayProperty=nameWithType> y lo almacena en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="ec981-104">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="ec981-105">La conversión unboxing extrae el tipo de valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="ec981-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="ec981-106">La conversión boxing es implícita y la conversión unboxing es explícita.</span><span class="sxs-lookup"><span data-stu-id="ec981-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="ec981-107">El concepto de conversión boxing y unboxing es la base de la vista unificada del sistema de tipos de C#, en el que un valor de cualquier tipo se puede tratar como objeto.</span><span class="sxs-lookup"><span data-stu-id="ec981-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="ec981-108">En el ejemplo siguiente, se aplica *conversión boxing* a la variable de entero `i` y esta se asigna al objeto `o`.</span><span class="sxs-lookup"><span data-stu-id="ec981-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="ec981-109">Luego se puede aplicar conversión unboxing al objeto `o` y asignarlo a la variable de entero `i`:</span><span class="sxs-lookup"><span data-stu-id="ec981-109">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="ec981-110">En los ejemplos siguientes se muestra cómo usar la conversión boxing en C#.</span><span class="sxs-lookup"><span data-stu-id="ec981-110">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="ec981-111">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="ec981-111">Performance</span></span>

<span data-ttu-id="ec981-112">Con relación a las asignaciones simples, las conversiones boxing y unboxing son procesos que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="ec981-112">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="ec981-113">Cuando se aplica la conversión boxing a un tipo de valor, se debe asignar y construir un objeto completamente nuevo.</span><span class="sxs-lookup"><span data-stu-id="ec981-113">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="ec981-114">En menor grado, la conversión de tipos requerida para aplicar la conversión unboxing también es costosa.</span><span class="sxs-lookup"><span data-stu-id="ec981-114">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="ec981-115">Para más información, vea [Rendimiento](../../../framework/performance/performance-tips.md).</span><span class="sxs-lookup"><span data-stu-id="ec981-115">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="ec981-116">Boxing</span><span class="sxs-lookup"><span data-stu-id="ec981-116">Boxing</span></span>

<span data-ttu-id="ec981-117">La conversión boxing se utiliza para almacenar tipos de valor en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec981-117">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="ec981-118">La conversión boxing es una conversión implícita de un [tipo de valor](../../language-reference/builtin-types/value-types.md) en el tipo `object` o en cualquier tipo de interfaz implementado por este tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ec981-118">Boxing is an implicit conversion of a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="ec981-119">Al aplicar la conversión boxing a un tipo de valor se asigna una instancia de objeto en el montón y se copia el valor en el nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="ec981-119">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="ec981-120">Considere la siguiente declaración de una variable de tipo de valor:</span><span class="sxs-lookup"><span data-stu-id="ec981-120">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="ec981-121">La siguiente instrucción aplica implícitamente la operación de conversión boxing en la variable `i`:</span><span class="sxs-lookup"><span data-stu-id="ec981-121">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="ec981-122">El resultado de esta instrucción es crear una referencia de objeto `o` en la pila que hace referencia a un valor del tipo `int` en el montón.</span><span class="sxs-lookup"><span data-stu-id="ec981-122">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="ec981-123">Este valor es una copia del tipo de valor asignado a la variable `i`.</span><span class="sxs-lookup"><span data-stu-id="ec981-123">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="ec981-124">La diferencia entre las dos variables, `i` y `o`, se muestra en la imagen siguiente de la conversión boxing:</span><span class="sxs-lookup"><span data-stu-id="ec981-124">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![Gráfico en el que se muestra la diferencia entre las variables i y o.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="ec981-126">También es posible realizar la conversión boxing de manera explícita, tal como se muestra en el ejemplo siguiente, pero esta nunca es necesaria:</span><span class="sxs-lookup"><span data-stu-id="ec981-126">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="ec981-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec981-127">Description</span></span>

<span data-ttu-id="ec981-128">Este ejemplo convierte una variable de entero `i` en un objeto `o` mediante la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="ec981-128">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="ec981-129">A continuación, el valor almacenado en la variable `i` se cambia de `123` a `456`.</span><span class="sxs-lookup"><span data-stu-id="ec981-129">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="ec981-130">El ejemplo muestra que el tipo de valor original y el objeto al que se ha aplicado la conversión boxing usan ubicaciones de memoria independientes y, por consiguiente, pueden almacenar valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="ec981-130">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="ec981-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec981-131">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="ec981-132">Conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="ec981-132">Unboxing</span></span>

<span data-ttu-id="ec981-133">La conversión unboxing es una conversión explícita del tipo `object` en un [tipo de valor](../../language-reference/builtin-types/value-types.md) o de un tipo de interfaz en un tipo de valor que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ec981-133">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/builtin-types/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="ec981-134">Una operación de conversión unboxing consiste en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec981-134">An unboxing operation consists of:</span></span>

- <span data-ttu-id="ec981-135">Comprobar la instancia de objeto para asegurarse de que se trata de un valor de conversión boxing del tipo de valor dado.</span><span class="sxs-lookup"><span data-stu-id="ec981-135">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="ec981-136">Copiar el valor de la instancia en la variable de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ec981-136">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="ec981-137">Las siguientes instrucciones muestran las operaciones de conversión boxing y unboxing:</span><span class="sxs-lookup"><span data-stu-id="ec981-137">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="ec981-138">En la figura siguiente se muestra el resultado de las instrucciones anteriores:</span><span class="sxs-lookup"><span data-stu-id="ec981-138">The following figure demonstrates the result of the previous statements:</span></span>

![Gráfico en el que se muestra una conversión unboxing.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="ec981-140">Para que la conversión unboxing de tipos de valor sea correcta en tiempo de ejecución, el elemento al que se aplica debe ser una referencia a un objeto creado previamente mediante la conversión boxing de una instancia de ese tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ec981-140">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="ec981-141">Si se intenta aplicar la conversión unboxing a `null`, se producirá una excepción <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="ec981-141">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="ec981-142">Si se intenta aplicar la conversión unboxing a una referencia de un tipo de valor incompatible, se producirá una excepción <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="ec981-142">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="ec981-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec981-143">Example</span></span>

<span data-ttu-id="ec981-144">El ejemplo siguiente muestra un caso de conversión unboxing no válida y la excepción `InvalidCastException` resultante.</span><span class="sxs-lookup"><span data-stu-id="ec981-144">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="ec981-145">Si se utiliza `try` y `catch`, se muestra un mensaje de error cuando se produce el error.</span><span class="sxs-lookup"><span data-stu-id="ec981-145">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="ec981-146">Este programa produce el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec981-146">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="ec981-147">Si cambia la instrucción:</span><span class="sxs-lookup"><span data-stu-id="ec981-147">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="ec981-148">a:</span><span class="sxs-lookup"><span data-stu-id="ec981-148">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="ec981-149">la conversión se realizará y se obtendrá el resultado:</span><span class="sxs-lookup"><span data-stu-id="ec981-149">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="ec981-150">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ec981-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ec981-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec981-151">See also</span></span>

- [<span data-ttu-id="ec981-152">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ec981-152">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ec981-153">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="ec981-153">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="ec981-154">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="ec981-154">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
