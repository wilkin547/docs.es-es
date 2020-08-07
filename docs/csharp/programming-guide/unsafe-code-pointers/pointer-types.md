---
title: Tipos de puntero - Guía de programación de C#
description: Aprenda sobre los tipos de puntero. Vea ejemplos de distintos punteros y ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 9c62a31f9a4a090fe56fb10ac45fe2f93f1b036e
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382040"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="413d6-104">Tipos de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="413d6-104">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="413d6-105">En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="413d6-105">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="413d6-106">Una declaración de tipos de puntero toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="413d6-106">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="413d6-107">El tipo especificado antes de `*` en un tipo de puntero se denomina **tipo referente**.</span><span class="sxs-lookup"><span data-stu-id="413d6-107">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="413d6-108">Solo un [tipo no administrado](../../language-reference/builtin-types/unmanaged-types.md) puede ser un tipo de referente.</span><span class="sxs-lookup"><span data-stu-id="413d6-108">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="413d6-109">Los tipos de puntero no heredan de [object](../../language-reference/builtin-types/reference-types.md) y no existe ninguna conversión entre tipos de puntero y `object`.</span><span class="sxs-lookup"><span data-stu-id="413d6-109">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="413d6-110">Además, las conversiones boxing y unboxing no admiten punteros.</span><span class="sxs-lookup"><span data-stu-id="413d6-110">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="413d6-111">Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="413d6-111">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="413d6-112">Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (\*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero.</span><span class="sxs-lookup"><span data-stu-id="413d6-112">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="413d6-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="413d6-113">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="413d6-114">Un puntero no puede señalar a una referencia ni a un [struct](../../language-reference/builtin-types/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale.</span><span class="sxs-lookup"><span data-stu-id="413d6-114">A pointer cannot point to a reference or to a [struct](../../language-reference/builtin-types/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="413d6-115">El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="413d6-115">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="413d6-116">El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`.</span><span class="sxs-lookup"><span data-stu-id="413d6-116">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="413d6-117">A continuación se muestran ejemplos de declaraciones de tipos de puntero:</span><span class="sxs-lookup"><span data-stu-id="413d6-117">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="413d6-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="413d6-118">Example</span></span>|<span data-ttu-id="413d6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="413d6-119">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="413d6-120">`p` es un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="413d6-120">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="413d6-121">`p` es un puntero a un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="413d6-121">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="413d6-122">`p` es una matriz unidimensional de punteros a enteros.</span><span class="sxs-lookup"><span data-stu-id="413d6-122">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="413d6-123">`p` es un puntero a un valor char.</span><span class="sxs-lookup"><span data-stu-id="413d6-123">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="413d6-124">`p` es un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="413d6-124">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="413d6-125">El operador de direccionamiento indirecto del puntero \* puede usarse para obtener acceso al contenido de la ubicación señalada por la variable de puntero.</span><span class="sxs-lookup"><span data-stu-id="413d6-125">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="413d6-126">Por ejemplo, consideremos la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="413d6-126">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="413d6-127">La expresión `*myVariable` denota la variable `int` que se encuentra en la dirección contenida en `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="413d6-127">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="413d6-128">Hay varios ejemplos de punteros en los temas [fixed (Instrucción)](../../language-reference/keywords/fixed-statement.md) y [Conversiones de puntero (Guía de programación de C#)](./pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="413d6-128">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="413d6-129">En el ejemplo siguiente se usa la palabra clave `unsafe` y la instrucción `fixed` y se muestra cómo incrementar un puntero interior.</span><span class="sxs-lookup"><span data-stu-id="413d6-129">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="413d6-130">Puede pegar este código en la función Main de una aplicación de consola para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="413d6-130">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="413d6-131">Estos ejemplos deben compilarse con el conjunto de opciones del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="413d6-131">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](snippets/FixedKeywordExamples.cs#5)]

<span data-ttu-id="413d6-132">No se puede aplicar el operador de direccionamiento indirecto a un puntero de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="413d6-132">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="413d6-133">Sin embargo, es posible usar una conversión para convertir un puntero void en cualquier otro tipo de puntero y viceversa.</span><span class="sxs-lookup"><span data-stu-id="413d6-133">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="413d6-134">Un puntero puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="413d6-134">A pointer can be `null`.</span></span> <span data-ttu-id="413d6-135">La aplicación del operador de direccionamiento indirecto a un puntero NULL da como resultado un comportamiento definido por la implementación.</span><span class="sxs-lookup"><span data-stu-id="413d6-135">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="413d6-136">Pasar punteros entre métodos puede provocar un comportamiento no definido.</span><span class="sxs-lookup"><span data-stu-id="413d6-136">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="413d6-137">Valore la posibilidad de usar un método que devuelva un puntero a una variable local mediante un parámetro `in`, `out` o `ref`, o bien como resultado de la función.</span><span class="sxs-lookup"><span data-stu-id="413d6-137">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="413d6-138">Si el puntero se estableció en un bloque fijo, es posible que la variable a la que señala ya no sea fija.</span><span class="sxs-lookup"><span data-stu-id="413d6-138">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="413d6-139">En la tabla siguiente se muestran los operadores e instrucciones que pueden funcionar en punteros en un contexto no seguro:</span><span class="sxs-lookup"><span data-stu-id="413d6-139">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="413d6-140">Operador/Instrucción</span><span class="sxs-lookup"><span data-stu-id="413d6-140">Operator/Statement</span></span>|<span data-ttu-id="413d6-141">Usar</span><span class="sxs-lookup"><span data-stu-id="413d6-141">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="413d6-142">Realiza el direccionamiento indirecto del puntero.</span><span class="sxs-lookup"><span data-stu-id="413d6-142">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="413d6-143">Obtiene acceso a un miembro de un struct a través de un puntero.</span><span class="sxs-lookup"><span data-stu-id="413d6-143">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="413d6-144">Indiza un puntero.</span><span class="sxs-lookup"><span data-stu-id="413d6-144">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="413d6-145">Obtiene la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="413d6-145">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="413d6-146">`++` y `--`</span><span class="sxs-lookup"><span data-stu-id="413d6-146">`++` and `--`</span></span>|<span data-ttu-id="413d6-147">Incrementa y disminuye los punteros.</span><span class="sxs-lookup"><span data-stu-id="413d6-147">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="413d6-148">`+` y `-`</span><span class="sxs-lookup"><span data-stu-id="413d6-148">`+` and `-`</span></span>|<span data-ttu-id="413d6-149">Realiza aritmética con punteros.</span><span class="sxs-lookup"><span data-stu-id="413d6-149">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="413d6-150">`==`, `!=`, `<`, `>`, `<=` y `>=`</span><span class="sxs-lookup"><span data-stu-id="413d6-150">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="413d6-151">Compara los punteros.</span><span class="sxs-lookup"><span data-stu-id="413d6-151">Compares pointers.</span></span>|
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="413d6-152">Asigna memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="413d6-152">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="413d6-153">Instrucción `fixed`</span><span class="sxs-lookup"><span data-stu-id="413d6-153">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="413d6-154">Fija provisionalmente una variable para que pueda encontrarse su dirección.</span><span class="sxs-lookup"><span data-stu-id="413d6-154">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="413d6-155">Para obtener más información sobre los operadores relacionados con el puntero, vea [Operadores relacionados con el puntero](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="413d6-155">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="413d6-156">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="413d6-156">C# language specification</span></span>

<span data-ttu-id="413d6-157">Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="413d6-157">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="413d6-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="413d6-158">See also</span></span>

- [<span data-ttu-id="413d6-159">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="413d6-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="413d6-160">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="413d6-160">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="413d6-161">Conversiones de puntero</span><span class="sxs-lookup"><span data-stu-id="413d6-161">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="413d6-162">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="413d6-162">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="413d6-163">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="413d6-163">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="413d6-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="413d6-164">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
