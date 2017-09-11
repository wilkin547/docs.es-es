---
title: sizeof (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 15d11071c369fad398d40cfef301e462c006d5e4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="sizeof-c-reference"></a><span data-ttu-id="a96ba-102">sizeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a96ba-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="a96ba-103">Se usa para obtener el tamaño en bytes de un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="a96ba-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="a96ba-104">Los tipos no administrados incluyen los tipos integrados que se muestran en la tabla que aparece a continuación, además de estos:</span><span class="sxs-lookup"><span data-stu-id="a96ba-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="a96ba-105">Tipos de enumeración</span><span class="sxs-lookup"><span data-stu-id="a96ba-105">Enum types</span></span>  
  
-   <span data-ttu-id="a96ba-106">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="a96ba-106">Pointer types</span></span>  
  
-   <span data-ttu-id="a96ba-107">Structs definidos por el usuario que no contienen ningún campo o propiedad que sea un tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="a96ba-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="a96ba-108">En el ejemplo siguiente, se muestra cómo recuperar el tamaño de un valor de tipo `int`:</span><span class="sxs-lookup"><span data-stu-id="a96ba-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="a96ba-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a96ba-109">Remarks</span></span>  
 <span data-ttu-id="a96ba-110">A partir de la versión 2.0 de C#, la aplicación de `sizeof` a los tipos integrados ya no necesita el uso del modo [no seguro](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="a96ba-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="a96ba-111">El operador `sizeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="a96ba-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="a96ba-112">Los valores devueltos por el operador `sizeof` son del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="a96ba-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="a96ba-113">En la tabla siguiente, se muestran los valores constantes que se sustituyen por expresiones `sizeof` que tienen determinados tipos integrados como operandos.</span><span class="sxs-lookup"><span data-stu-id="a96ba-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="a96ba-114">Expresión</span><span class="sxs-lookup"><span data-stu-id="a96ba-114">Expression</span></span>|<span data-ttu-id="a96ba-115">Valor constante</span><span class="sxs-lookup"><span data-stu-id="a96ba-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="a96ba-116">1</span><span class="sxs-lookup"><span data-stu-id="a96ba-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="a96ba-117">1</span><span class="sxs-lookup"><span data-stu-id="a96ba-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="a96ba-118">2</span><span class="sxs-lookup"><span data-stu-id="a96ba-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="a96ba-119">2</span><span class="sxs-lookup"><span data-stu-id="a96ba-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="a96ba-120">4</span><span class="sxs-lookup"><span data-stu-id="a96ba-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="a96ba-121">4</span><span class="sxs-lookup"><span data-stu-id="a96ba-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="a96ba-122">8</span><span class="sxs-lookup"><span data-stu-id="a96ba-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="a96ba-123">8</span><span class="sxs-lookup"><span data-stu-id="a96ba-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="a96ba-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="a96ba-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="a96ba-125">4</span><span class="sxs-lookup"><span data-stu-id="a96ba-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="a96ba-126">8</span><span class="sxs-lookup"><span data-stu-id="a96ba-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="a96ba-127">16</span><span class="sxs-lookup"><span data-stu-id="a96ba-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="a96ba-128">1</span><span class="sxs-lookup"><span data-stu-id="a96ba-128">1</span></span>|  
  
 <span data-ttu-id="a96ba-129">Para todos los demás tipos, incluidos los structs, el operador `sizeof` se puede usar únicamente en bloques de código no seguro.</span><span class="sxs-lookup"><span data-stu-id="a96ba-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="a96ba-130">Aunque puede usar el método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>, el valor devuelto mediante este método no es siempre el mismo que el valor devuelto por `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="a96ba-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="a96ba-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> devuelve el tamaño una vez calculado el tipo, mientras que `sizeof` devuelve el tamaño asignado por Common Language Runtime, incluido el relleno.</span><span class="sxs-lookup"><span data-stu-id="a96ba-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a96ba-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a96ba-132">Example</span></span>  
 <span data-ttu-id="a96ba-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a96ba-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a96ba-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a96ba-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a96ba-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a96ba-135">See Also</span></span>  
 <span data-ttu-id="a96ba-136">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a96ba-137">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a96ba-138">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a96ba-139">[Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="a96ba-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span></span>  
 <span data-ttu-id="a96ba-141">[Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-141">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="a96ba-142">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="a96ba-142">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="a96ba-143">Constantes</span><span class="sxs-lookup"><span data-stu-id="a96ba-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

