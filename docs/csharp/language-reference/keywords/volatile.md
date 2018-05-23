---
title: volatile (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 7f3aafc1255667f2a3917c6e171ce4ddf0343b41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="volatile-c-reference"></a><span data-ttu-id="efd86-102">volatile (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="efd86-102">volatile (C# Reference)</span></span>
<span data-ttu-id="efd86-103">La palabra clave `volatile` indica que un campo puede ser modificado por varios subprocesos que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="efd86-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="efd86-104">Los campos declarados como `volatile` no están sujetos a optimizaciones del compilador que dan por hecho el acceso por parte de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="efd86-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="efd86-105">Esto garantiza que el valor más actualizado esté presente en el campo en todo momento.</span><span class="sxs-lookup"><span data-stu-id="efd86-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="efd86-106">El modificador `volatile` normalmente se usa para un campo al que acceden varios subprocesos sin emplear la instrucción [lock](../../../csharp/language-reference/keywords/lock-statement.md) para serializar el acceso.</span><span class="sxs-lookup"><span data-stu-id="efd86-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="efd86-107">La palabra clave `volatile` se puede aplicar a campos de estos tipos:</span><span class="sxs-lookup"><span data-stu-id="efd86-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="efd86-108">Tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="efd86-108">Reference types.</span></span>  
  
-   <span data-ttu-id="efd86-109">Tipos de puntero (en un contexto no seguro).</span><span class="sxs-lookup"><span data-stu-id="efd86-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="efd86-110">Observe que aunque el propio puntero puede ser volatile, no el objeto al que apunta.</span><span class="sxs-lookup"><span data-stu-id="efd86-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="efd86-111">Es decir, no puede declarar un "puntero a volatile".</span><span class="sxs-lookup"><span data-stu-id="efd86-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="efd86-112">Tipos como sbyte, byte, short, ushort, int, uint, char, float y bool.</span><span class="sxs-lookup"><span data-stu-id="efd86-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="efd86-113">Un tipo enum con uno de los siguientes tipos base: byte, sbyte, short, ushort, int o uint.</span><span class="sxs-lookup"><span data-stu-id="efd86-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="efd86-114">Parámetros de tipo genérico que se sabe que son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="efd86-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="efd86-115"><xref:System.IntPtr> y <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="efd86-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="efd86-116">La palabra clave volatile solo puede aplicarse a campos de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="efd86-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="efd86-117">Las variables locales no se pueden declarar como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="efd86-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efd86-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efd86-118">Example</span></span>  
 <span data-ttu-id="efd86-119">En el ejemplo siguiente se muestra cómo declarar una variable de campo pública como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="efd86-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="efd86-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efd86-120">Example</span></span>  
 <span data-ttu-id="efd86-121">En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo y usarlo para realizar el procesamiento en paralelo con el del subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="efd86-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="efd86-122">Para obtener información general sobre el multithreading, vea [Subprocesamiento (C#)](../../../standard/threading/index.md) y [Subprocesamiento administrado](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="efd86-122">For background information about multithreading, see [Threading (C#)](../../../standard/threading/index.md) and [Managed Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="efd86-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="efd86-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efd86-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="efd86-124">See Also</span></span>  
 [<span data-ttu-id="efd86-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="efd86-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="efd86-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="efd86-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="efd86-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="efd86-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="efd86-128">Modificadores</span><span class="sxs-lookup"><span data-stu-id="efd86-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
