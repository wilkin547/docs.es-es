---
title: sizeof (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 37eb9345edc31a8d318540fd528f311059225de4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184210"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="393a2-102">sizeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="393a2-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="393a2-103">Se usa para obtener el tamaño en bytes de un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="393a2-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="393a2-104">Los tipos no administrados incluyen:</span><span class="sxs-lookup"><span data-stu-id="393a2-104">Unmanaged types include:</span></span>

- <span data-ttu-id="393a2-105">Los tipos simples se enumeran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="393a2-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="393a2-106">Expresión</span><span class="sxs-lookup"><span data-stu-id="393a2-106">Expression</span></span>|<span data-ttu-id="393a2-107">Valor constante</span><span class="sxs-lookup"><span data-stu-id="393a2-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="393a2-108">1</span><span class="sxs-lookup"><span data-stu-id="393a2-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="393a2-109">1</span><span class="sxs-lookup"><span data-stu-id="393a2-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="393a2-110">2</span><span class="sxs-lookup"><span data-stu-id="393a2-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="393a2-111">2</span><span class="sxs-lookup"><span data-stu-id="393a2-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="393a2-112">4</span><span class="sxs-lookup"><span data-stu-id="393a2-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="393a2-113">4</span><span class="sxs-lookup"><span data-stu-id="393a2-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="393a2-114">8</span><span class="sxs-lookup"><span data-stu-id="393a2-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="393a2-115">8</span><span class="sxs-lookup"><span data-stu-id="393a2-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="393a2-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="393a2-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="393a2-117">4</span><span class="sxs-lookup"><span data-stu-id="393a2-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="393a2-118">8</span><span class="sxs-lookup"><span data-stu-id="393a2-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="393a2-119">16</span><span class="sxs-lookup"><span data-stu-id="393a2-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="393a2-120">1</span><span class="sxs-lookup"><span data-stu-id="393a2-120">1</span></span>|

- <span data-ttu-id="393a2-121">Tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="393a2-121">Enum types.</span></span>

- <span data-ttu-id="393a2-122">Tipos de puntero.</span><span class="sxs-lookup"><span data-stu-id="393a2-122">Pointer types.</span></span>

- <span data-ttu-id="393a2-123">Estructuras definidas por el usuario que no contienen los campos de instancia o las propiedades de instancia implementadas automáticamente que son tipos de referencia o tipos construidos.</span><span class="sxs-lookup"><span data-stu-id="393a2-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="393a2-124">En el ejemplo siguiente, se muestra cómo recuperar el tamaño de un valor de tipo `int`:</span><span class="sxs-lookup"><span data-stu-id="393a2-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="393a2-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="393a2-125">Remarks</span></span>

<span data-ttu-id="393a2-126">A partir de la versión 2.0 de C#, para aplicar `sizeof` a tipos simples o de enumeración ya no se requiere que el código se compile en un contexto [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="393a2-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="393a2-127">El operador `sizeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="393a2-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="393a2-128">Los valores devueltos por el operador `sizeof` son del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="393a2-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="393a2-129">En la tabla anterior, se muestran los valores constantes que se sustituyen por expresiones `sizeof` que tienen determinados tipos simples como operandos.</span><span class="sxs-lookup"><span data-stu-id="393a2-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="393a2-130">Para todos los demás tipos, incluidos los structs, el operador `sizeof` se puede usar únicamente en bloques de código no seguro.</span><span class="sxs-lookup"><span data-stu-id="393a2-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="393a2-131">Aunque puede usar el método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, el valor devuelto mediante este método no es siempre el mismo que el valor devuelto por `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="393a2-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="393a2-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> devuelve el tamaño una vez calculado el tipo, mientras que `sizeof` devuelve el tamaño asignado por Common Language Runtime, incluido el relleno.</span><span class="sxs-lookup"><span data-stu-id="393a2-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="393a2-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="393a2-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="393a2-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="393a2-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="393a2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="393a2-135">See also</span></span>

- [<span data-ttu-id="393a2-136">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="393a2-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="393a2-137">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="393a2-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="393a2-138">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="393a2-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="393a2-139">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="393a2-139">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="393a2-140">enum</span><span class="sxs-lookup"><span data-stu-id="393a2-140">enum</span></span>](enum.md)
- [<span data-ttu-id="393a2-141">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="393a2-141">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="393a2-142">Structs</span><span class="sxs-lookup"><span data-stu-id="393a2-142">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="393a2-143">Constantes</span><span class="sxs-lookup"><span data-stu-id="393a2-143">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)