---
title: volatile (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cefa39313c3c551e8d05fbc31e528b86c6888d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="volatile-c-reference"></a><span data-ttu-id="99a8e-102">volatile (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="99a8e-102">volatile (C# Reference)</span></span>
<span data-ttu-id="99a8e-103">La palabra clave `volatile` indica que un campo puede ser modificado por varios subprocesos que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="99a8e-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="99a8e-104">Los campos declarados como `volatile` no están sujetos a optimizaciones del compilador que dan por hecho el acceso por parte de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="99a8e-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="99a8e-105">Esto garantiza que el valor más actualizado esté presente en el campo en todo momento.</span><span class="sxs-lookup"><span data-stu-id="99a8e-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="99a8e-106">El modificador `volatile` normalmente se usa para un campo al que acceden varios subprocesos sin emplear la instrucción [lock](../../../csharp/language-reference/keywords/lock-statement.md) para serializar el acceso.</span><span class="sxs-lookup"><span data-stu-id="99a8e-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="99a8e-107">La palabra clave `volatile` se puede aplicar a campos de estos tipos:</span><span class="sxs-lookup"><span data-stu-id="99a8e-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="99a8e-108">Tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="99a8e-108">Reference types.</span></span>  
  
-   <span data-ttu-id="99a8e-109">Tipos de puntero (en un contexto no seguro).</span><span class="sxs-lookup"><span data-stu-id="99a8e-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="99a8e-110">Observe que aunque el propio puntero puede ser volatile, no el objeto al que apunta.</span><span class="sxs-lookup"><span data-stu-id="99a8e-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="99a8e-111">Es decir, no puede declarar un "puntero a volatile".</span><span class="sxs-lookup"><span data-stu-id="99a8e-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="99a8e-112">Tipos como sbyte, byte, short, ushort, int, uint, char, float y bool.</span><span class="sxs-lookup"><span data-stu-id="99a8e-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="99a8e-113">Un tipo enum con uno de los siguientes tipos base: byte, sbyte, short, ushort, int o uint.</span><span class="sxs-lookup"><span data-stu-id="99a8e-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="99a8e-114">Parámetros de tipo genérico que se sabe que son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="99a8e-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="99a8e-115"><xref:System.IntPtr> y <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="99a8e-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="99a8e-116">La palabra clave volatile solo puede aplicarse a campos de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="99a8e-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="99a8e-117">Las variables locales no se pueden declarar como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="99a8e-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99a8e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99a8e-118">Example</span></span>  
 <span data-ttu-id="99a8e-119">En el ejemplo siguiente se muestra cómo declarar una variable de campo pública como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="99a8e-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="99a8e-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99a8e-120">Example</span></span>  
 <span data-ttu-id="99a8e-121">En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo y usarlo para realizar el procesamiento en paralelo con el del subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="99a8e-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="99a8e-122">Para obtener información general sobre multithreading, vea [Subprocesamiento](../../../standard/threading/index.md) y [Subprocesamiento](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="99a8e-122">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="99a8e-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="99a8e-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99a8e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="99a8e-124">See Also</span></span>  
 [<span data-ttu-id="99a8e-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="99a8e-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="99a8e-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="99a8e-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="99a8e-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="99a8e-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="99a8e-128">Modificadores</span><span class="sxs-lookup"><span data-stu-id="99a8e-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
