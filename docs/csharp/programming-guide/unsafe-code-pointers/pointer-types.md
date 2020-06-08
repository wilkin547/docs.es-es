---
title: Tipos de puntero - Guía de programación de C#
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 492b37460c05ffbc82e020facb354be22706f8d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396264"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="5cae4-102">Tipos de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5cae4-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="5cae4-103">En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="5cae4-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="5cae4-104">Una declaración de tipos de puntero toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="5cae4-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="5cae4-105">El tipo especificado antes de `*` en un tipo de puntero se denomina **tipo referente**.</span><span class="sxs-lookup"><span data-stu-id="5cae4-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="5cae4-106">Solo un [tipo no administrado](../../language-reference/builtin-types/unmanaged-types.md) puede ser un tipo de referente.</span><span class="sxs-lookup"><span data-stu-id="5cae4-106">Only an [unmanaged type](../../language-reference/builtin-types/unmanaged-types.md) can be a referent type.</span></span>

<span data-ttu-id="5cae4-107">Los tipos de puntero no heredan de [object](../../language-reference/builtin-types/reference-types.md) y no existe ninguna conversión entre tipos de puntero y `object`.</span><span class="sxs-lookup"><span data-stu-id="5cae4-107">Pointer types do not inherit from [object](../../language-reference/builtin-types/reference-types.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="5cae4-108">Además, las conversiones boxing y unboxing no admiten punteros.</span><span class="sxs-lookup"><span data-stu-id="5cae4-108">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="5cae4-109">Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="5cae4-109">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="5cae4-110">Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (\*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-110">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="5cae4-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5cae4-111">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="5cae4-112">Un puntero no puede señalar a una referencia ni a un [struct](../../language-reference/builtin-types/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale.</span><span class="sxs-lookup"><span data-stu-id="5cae4-112">A pointer cannot point to a reference or to a [struct](../../language-reference/builtin-types/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="5cae4-113">El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="5cae4-113">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="5cae4-114">El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`.</span><span class="sxs-lookup"><span data-stu-id="5cae4-114">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="5cae4-115">A continuación se muestran ejemplos de declaraciones de tipos de puntero:</span><span class="sxs-lookup"><span data-stu-id="5cae4-115">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="5cae4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cae4-116">Example</span></span>|<span data-ttu-id="5cae4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cae4-117">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="5cae4-118">`p` es un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-118">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="5cae4-119">`p` es un puntero a un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-119">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="5cae4-120">`p` es una matriz unidimensional de punteros a enteros.</span><span class="sxs-lookup"><span data-stu-id="5cae4-120">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="5cae4-121">`p` es un puntero a un valor char.</span><span class="sxs-lookup"><span data-stu-id="5cae4-121">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="5cae4-122">`p` es un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="5cae4-122">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="5cae4-123">El operador de direccionamiento indirecto del puntero \* puede usarse para obtener acceso al contenido de la ubicación señalada por la variable de puntero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-123">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="5cae4-124">Por ejemplo, consideremos la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="5cae4-124">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="5cae4-125">La expresión `*myVariable` denota la variable `int` que se encuentra en la dirección contenida en `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="5cae4-125">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="5cae4-126">Hay varios ejemplos de punteros en los temas [fixed (Instrucción)](../../language-reference/keywords/fixed-statement.md) y [Conversiones de puntero (Guía de programación de C#)](./pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="5cae4-126">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](./pointer-conversions.md).</span></span> <span data-ttu-id="5cae4-127">En el ejemplo siguiente se usa la palabra clave `unsafe` y la instrucción `fixed` y se muestra cómo incrementar un puntero interior.</span><span class="sxs-lookup"><span data-stu-id="5cae4-127">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="5cae4-128">Puede pegar este código en la función Main de una aplicación de consola para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="5cae4-128">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="5cae4-129">Estos ejemplos deben compilarse con el conjunto de opciones del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5cae4-129">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](snippets/FixedKeywordExamples.cs#5)]

<span data-ttu-id="5cae4-130">No se puede aplicar el operador de direccionamiento indirecto a un puntero de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="5cae4-130">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="5cae4-131">Sin embargo, es posible usar una conversión para convertir un puntero void en cualquier otro tipo de puntero y viceversa.</span><span class="sxs-lookup"><span data-stu-id="5cae4-131">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="5cae4-132">Un puntero puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="5cae4-132">A pointer can be `null`.</span></span> <span data-ttu-id="5cae4-133">La aplicación del operador de direccionamiento indirecto a un puntero NULL da como resultado un comportamiento definido por la implementación.</span><span class="sxs-lookup"><span data-stu-id="5cae4-133">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="5cae4-134">Pasar punteros entre métodos puede provocar un comportamiento no definido.</span><span class="sxs-lookup"><span data-stu-id="5cae4-134">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="5cae4-135">Valore la posibilidad de usar un método que devuelva un puntero a una variable local mediante un parámetro `in`, `out` o `ref`, o bien como resultado de la función.</span><span class="sxs-lookup"><span data-stu-id="5cae4-135">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="5cae4-136">Si el puntero se estableció en un bloque fijo, es posible que la variable a la que señala ya no sea fija.</span><span class="sxs-lookup"><span data-stu-id="5cae4-136">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="5cae4-137">En la tabla siguiente se muestran los operadores e instrucciones que pueden funcionar en punteros en un contexto no seguro:</span><span class="sxs-lookup"><span data-stu-id="5cae4-137">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="5cae4-138">Operador/Instrucción</span><span class="sxs-lookup"><span data-stu-id="5cae4-138">Operator/Statement</span></span>|<span data-ttu-id="5cae4-139">Usar</span><span class="sxs-lookup"><span data-stu-id="5cae4-139">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="5cae4-140">Realiza el direccionamiento indirecto del puntero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-140">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="5cae4-141">Obtiene acceso a un miembro de un struct a través de un puntero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-141">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="5cae4-142">Indiza un puntero.</span><span class="sxs-lookup"><span data-stu-id="5cae4-142">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="5cae4-143">Obtiene la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="5cae4-143">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="5cae4-144">`++` y `--`</span><span class="sxs-lookup"><span data-stu-id="5cae4-144">`++` and `--`</span></span>|<span data-ttu-id="5cae4-145">Incrementa y disminuye los punteros.</span><span class="sxs-lookup"><span data-stu-id="5cae4-145">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="5cae4-146">`+` y `-`</span><span class="sxs-lookup"><span data-stu-id="5cae4-146">`+` and `-`</span></span>|<span data-ttu-id="5cae4-147">Realiza aritmética con punteros.</span><span class="sxs-lookup"><span data-stu-id="5cae4-147">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="5cae4-148">`==`, `!=`, `<`, `>`, `<=` y `>=`</span><span class="sxs-lookup"><span data-stu-id="5cae4-148">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="5cae4-149">Compara los punteros.</span><span class="sxs-lookup"><span data-stu-id="5cae4-149">Compares pointers.</span></span>|
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="5cae4-150">Asigna memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="5cae4-150">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="5cae4-151">Instrucción `fixed`</span><span class="sxs-lookup"><span data-stu-id="5cae4-151">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="5cae4-152">Fija provisionalmente una variable para que pueda encontrarse su dirección.</span><span class="sxs-lookup"><span data-stu-id="5cae4-152">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="5cae4-153">Para obtener más información sobre los operadores relacionados con el puntero, vea [Operadores relacionados con el puntero](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5cae4-153">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5cae4-154">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5cae4-154">C# language specification</span></span>

<span data-ttu-id="5cae4-155">Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5cae4-155">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5cae4-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cae4-156">See also</span></span>

- [<span data-ttu-id="5cae4-157">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5cae4-157">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5cae4-158">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="5cae4-158">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="5cae4-159">Conversiones de puntero</span><span class="sxs-lookup"><span data-stu-id="5cae4-159">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="5cae4-160">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="5cae4-160">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="5cae4-161">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="5cae4-161">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="5cae4-162">unsafe</span><span class="sxs-lookup"><span data-stu-id="5cae4-162">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
