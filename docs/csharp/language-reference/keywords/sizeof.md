---
title: sizeof (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 83038255160ec778c71120566cf8f99092761add
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270583"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="0d56a-102">sizeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0d56a-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="0d56a-103">Se usa para obtener el tamaño en bytes de un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="0d56a-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="0d56a-104">Los tipos no administrados incluyen los tipos integrados que se muestran en la tabla que aparece a continuación, además de estos:</span><span class="sxs-lookup"><span data-stu-id="0d56a-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="0d56a-105">Tipos de enumeración</span><span class="sxs-lookup"><span data-stu-id="0d56a-105">Enum types</span></span>  
  
-   <span data-ttu-id="0d56a-106">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="0d56a-106">Pointer types</span></span>  
  
-   <span data-ttu-id="0d56a-107">Structs definidos por el usuario que no contienen ningún campo o propiedad que sea un tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="0d56a-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="0d56a-108">En el ejemplo siguiente, se muestra cómo recuperar el tamaño de un valor de tipo `int`:</span><span class="sxs-lookup"><span data-stu-id="0d56a-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="0d56a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d56a-109">Remarks</span></span>  
 <span data-ttu-id="0d56a-110">A partir de la versión 2.0 de C#, la aplicación de `sizeof` a los tipos integrados ya no necesita el uso del modo [no seguro](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="0d56a-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="0d56a-111">El operador `sizeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="0d56a-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="0d56a-112">Los valores devueltos por el operador `sizeof` son del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="0d56a-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="0d56a-113">En la tabla siguiente, se muestran los valores constantes que se sustituyen por expresiones `sizeof` que tienen determinados tipos integrados como operandos.</span><span class="sxs-lookup"><span data-stu-id="0d56a-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="0d56a-114">Expresión</span><span class="sxs-lookup"><span data-stu-id="0d56a-114">Expression</span></span>|<span data-ttu-id="0d56a-115">Valor constante</span><span class="sxs-lookup"><span data-stu-id="0d56a-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="0d56a-116">1</span><span class="sxs-lookup"><span data-stu-id="0d56a-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="0d56a-117">1</span><span class="sxs-lookup"><span data-stu-id="0d56a-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="0d56a-118">2</span><span class="sxs-lookup"><span data-stu-id="0d56a-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="0d56a-119">2</span><span class="sxs-lookup"><span data-stu-id="0d56a-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="0d56a-120">4</span><span class="sxs-lookup"><span data-stu-id="0d56a-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="0d56a-121">4</span><span class="sxs-lookup"><span data-stu-id="0d56a-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="0d56a-122">8</span><span class="sxs-lookup"><span data-stu-id="0d56a-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="0d56a-123">8</span><span class="sxs-lookup"><span data-stu-id="0d56a-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="0d56a-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="0d56a-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="0d56a-125">4</span><span class="sxs-lookup"><span data-stu-id="0d56a-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="0d56a-126">8</span><span class="sxs-lookup"><span data-stu-id="0d56a-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="0d56a-127">16</span><span class="sxs-lookup"><span data-stu-id="0d56a-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="0d56a-128">1</span><span class="sxs-lookup"><span data-stu-id="0d56a-128">1</span></span>|  
  
 <span data-ttu-id="0d56a-129">Para todos los demás tipos, incluidos los structs, el operador `sizeof` se puede usar únicamente en bloques de código no seguro.</span><span class="sxs-lookup"><span data-stu-id="0d56a-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="0d56a-130">Aunque puede usar el método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, el valor devuelto mediante este método no es siempre el mismo que el valor devuelto por `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="0d56a-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="0d56a-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> devuelve el tamaño una vez calculado el tipo, mientras que `sizeof` devuelve el tamaño asignado por Common Language Runtime, incluido el relleno.</span><span class="sxs-lookup"><span data-stu-id="0d56a-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d56a-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d56a-132">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d56a-133">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0d56a-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d56a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d56a-134">See Also</span></span>  
 [<span data-ttu-id="0d56a-135">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0d56a-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0d56a-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0d56a-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0d56a-137">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0d56a-137">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0d56a-138">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="0d56a-138">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="0d56a-139">enum</span><span class="sxs-lookup"><span data-stu-id="0d56a-139">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
 [<span data-ttu-id="0d56a-140">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="0d56a-140">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="0d56a-141">Structs</span><span class="sxs-lookup"><span data-stu-id="0d56a-141">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="0d56a-142">Constantes</span><span class="sxs-lookup"><span data-stu-id="0d56a-142">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
