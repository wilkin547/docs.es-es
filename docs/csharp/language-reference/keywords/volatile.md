---
title: volatile - Referencia de C#
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: c7a6c442c33ac2b41f652805837f455a957819de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712850"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="688b7-102">volatile (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="688b7-102">volatile (C# Reference)</span></span>

<span data-ttu-id="688b7-103">La palabra clave `volatile` indica que un campo puede ser modificado por varios subprocesos que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="688b7-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="688b7-104">El compilador, el sistema de runtime e incluso el hardware pueden reorganizar las lecturas y escrituras en las ubicaciones de memoria por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="688b7-104">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="688b7-105">Los campos que se declaran `volatile` no están sujetos a estas optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="688b7-105">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="688b7-106">La incorporación del modificador `volatile` asegura que todos los subprocesos observarán las operaciones de escritura volátiles realizadas por cualquier otro subproceso en el orden en que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="688b7-106">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="688b7-107">No hay ninguna garantía de una única ordenación total de las operaciones de escritura volátiles como se muestra en todos los subprocesos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="688b7-107">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="688b7-108">La palabra clave `volatile` se puede aplicar a campos de estos tipos:</span><span class="sxs-lookup"><span data-stu-id="688b7-108">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="688b7-109">Tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="688b7-109">Reference types.</span></span>
- <span data-ttu-id="688b7-110">Tipos de puntero (en un contexto no seguro).</span><span class="sxs-lookup"><span data-stu-id="688b7-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="688b7-111">Observe que aunque el propio puntero puede ser volatile, no el objeto al que apunta.</span><span class="sxs-lookup"><span data-stu-id="688b7-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="688b7-112">Es decir, no puede declarar un "puntero a volatile".</span><span class="sxs-lookup"><span data-stu-id="688b7-112">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="688b7-113">Tipos simples como `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` y `bool`.</span><span class="sxs-lookup"><span data-stu-id="688b7-113">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="688b7-114">Un tipo `enum` con uno de los siguientes tipos base: `byte`, `sbyte`, `short`, `ushort`, `int` o `uint`.</span><span class="sxs-lookup"><span data-stu-id="688b7-114">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="688b7-115">Parámetros de tipo genérico que se sabe que son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="688b7-115">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="688b7-116"><xref:System.IntPtr> y <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="688b7-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="688b7-117">Otros tipos, incluidos `double` y `long`, no pueden marcarse como `volatile` porque no se puede garantizar que las lecturas y escrituras los campos de esos tipos sean atómicas.</span><span class="sxs-lookup"><span data-stu-id="688b7-117">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="688b7-118">Para proteger el acceso multiproceso a esos tipos de campos, use los miembros de clase <xref:System.Threading.Interlocked> o proteja el acceso mediante la instrucción [`lock`](lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="688b7-118">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="688b7-119">La palabra clave `volatile` solo se puede aplicar a campos de `class` o `struct`.</span><span class="sxs-lookup"><span data-stu-id="688b7-119">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="688b7-120">Las variables locales no se pueden declarar como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="688b7-120">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="688b7-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="688b7-121">Example</span></span>

<span data-ttu-id="688b7-122">En el ejemplo siguiente se muestra cómo declarar una variable de campo pública como `volatile`.</span><span class="sxs-lookup"><span data-stu-id="688b7-122">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="688b7-123">En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo y usarlo para realizar el procesamiento en paralelo con el del subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="688b7-123">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="688b7-124">Para más información sobre el multithreading, vea [Subprocesamiento administrado](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="688b7-124">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="688b7-125">Con el modificador `volatile` que se agrega a la declaración de `_shouldStop` en su lugar, siempre obtendrá los mismos resultados (similar al fragmento que se muestra en el código anterior).</span><span class="sxs-lookup"><span data-stu-id="688b7-125">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="688b7-126">Sin embargo, sin ese modificador en el miembro `_shouldStop`, el comportamiento es imprevisible.</span><span class="sxs-lookup"><span data-stu-id="688b7-126">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="688b7-127">El método `DoWork` puede optimizar el acceso a los miembros, lo que provoca la lectura de datos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="688b7-127">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="688b7-128">Dada la naturaleza de la programación multiproceso, el número de lecturas obsoletas es imprevisible.</span><span class="sxs-lookup"><span data-stu-id="688b7-128">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="688b7-129">Distintas ejecuciones del programa generarán resultados ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="688b7-129">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="688b7-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="688b7-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="688b7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="688b7-131">See also</span></span>

- [<span data-ttu-id="688b7-132">Especificación del lenguaje C#: palabra clave volatile</span><span class="sxs-lookup"><span data-stu-id="688b7-132">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="688b7-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="688b7-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="688b7-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="688b7-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="688b7-135">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="688b7-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="688b7-136">Modificadores</span><span class="sxs-lookup"><span data-stu-id="688b7-136">Modifiers</span></span>](index.md)
- [<span data-ttu-id="688b7-137">lock (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="688b7-137">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
