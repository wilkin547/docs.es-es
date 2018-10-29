---
title: unsafe (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: f4fcff02166091ae5dbd83e7ddf7762373fd9836
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086458"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="3d2ad-102">unsafe (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3d2ad-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="3d2ad-103">La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros.</span><span class="sxs-lookup"><span data-stu-id="3d2ad-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="3d2ad-104">Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="3d2ad-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="3d2ad-105">Puede usar el codificador `unsafe` en la declaración de un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="3d2ad-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="3d2ad-106">Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="3d2ad-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="3d2ad-107">Por ejemplo, el siguiente método se declara con el modificador `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="3d2ad-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```csharp  
unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="3d2ad-108">El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:</span><span class="sxs-lookup"><span data-stu-id="3d2ad-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="3d2ad-109">También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque.</span><span class="sxs-lookup"><span data-stu-id="3d2ad-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="3d2ad-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3d2ad-110">For example:</span></span>  
  
```csharp  
unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="3d2ad-111">Para compilar código no seguro, debe especificar la opción [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="3d2ad-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="3d2ad-112">Common Language Runtime no puede comprobar el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="3d2ad-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d2ad-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d2ad-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="3d2ad-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3d2ad-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d2ad-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d2ad-115">See Also</span></span>

- [<span data-ttu-id="3d2ad-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3d2ad-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3d2ad-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3d2ad-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3d2ad-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3d2ad-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="3d2ad-119">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3d2ad-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="3d2ad-120">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="3d2ad-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="3d2ad-121">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="3d2ad-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
