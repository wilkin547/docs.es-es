---
title: volatile (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253172"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="3786b-102">volatile (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3786b-102">volatile (C# Reference)</span></span>
<span data-ttu-id="3786b-103">La palabra clave `volatile` indica que un campo puede ser modificado por varios subprocesos que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3786b-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="3786b-104">Los campos declarados como `volatile` no están sujetos a optimizaciones del compilador que dan por hecho el acceso por parte de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="3786b-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="3786b-105">Estas restricciones aseguran que todos los subprocesos observarán las operaciones de escritura volátiles realizadas por cualquier otro subproceso en el orden en que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="3786b-105">These restrictions ensure that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="3786b-106">No hay ninguna garantía de una única ordenación total de las operaciones de escritura volátiles como se muestra en todos los subprocesos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3786b-106">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>  
  
 <span data-ttu-id="3786b-107">El modificador `volatile` normalmente se usa para un campo al que acceden varios subprocesos sin emplear la instrucción [lock](../../../csharp/language-reference/keywords/lock-statement.md) para serializar el acceso.</span><span class="sxs-lookup"><span data-stu-id="3786b-107">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="3786b-108">La palabra clave `volatile` se puede aplicar a campos de estos tipos:</span><span class="sxs-lookup"><span data-stu-id="3786b-108">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="3786b-109">Tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="3786b-109">Reference types.</span></span>  
  
-   <span data-ttu-id="3786b-110">Tipos de puntero (en un contexto no seguro).</span><span class="sxs-lookup"><span data-stu-id="3786b-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="3786b-111">Observe que aunque el propio puntero puede ser volatile, no el objeto al que apunta.</span><span class="sxs-lookup"><span data-stu-id="3786b-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="3786b-112">Es decir, no puede declarar un "puntero a volatile".</span><span class="sxs-lookup"><span data-stu-id="3786b-112">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="3786b-113">Tipos como sbyte, byte, short, ushort, int, uint, char, float y bool.</span><span class="sxs-lookup"><span data-stu-id="3786b-113">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="3786b-114">Un tipo enum con uno de los siguientes tipos base: byte, sbyte, short, ushort, int o uint.</span><span class="sxs-lookup"><span data-stu-id="3786b-114">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="3786b-115">Parámetros de tipo genérico que se sabe que son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="3786b-115">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="3786b-116"><xref:System.IntPtr> y <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="3786b-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="3786b-117">La palabra clave volatile solo puede aplicarse a campos de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="3786b-117">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="3786b-118">Las variables locales no se pueden declarar como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="3786b-118">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3786b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3786b-119">Example</span></span>  
 <span data-ttu-id="3786b-120">En el ejemplo siguiente se muestra cómo declarar una variable de campo pública como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="3786b-120">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="3786b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3786b-121">Example</span></span>  
 <span data-ttu-id="3786b-122">En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo y usarlo para realizar el procesamiento en paralelo con el del subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="3786b-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="3786b-123">Para obtener información general sobre el multithreading, vea [Subprocesamiento administrado](../../../standard/threading/index.md) y [Subprocesamiento (C#)](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="3786b-123">For background information about multithreading, see [Managed Threading](../../../standard/threading/index.md) and [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="3786b-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3786b-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3786b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3786b-125">See Also</span></span>

- [<span data-ttu-id="3786b-126">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3786b-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3786b-127">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3786b-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3786b-128">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3786b-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="3786b-129">Modificadores</span><span class="sxs-lookup"><span data-stu-id="3786b-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
