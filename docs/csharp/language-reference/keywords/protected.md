---
description: 'Palabra clave protected: Referencia de C#'
title: 'Palabra clave protected: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: d8d9a75bb5e07816adaa8d09c96cee8a240130fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688918"
---
# <a name="protected-c-reference"></a><span data-ttu-id="c66fc-103">protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c66fc-103">protected (C# Reference)</span></span>

<span data-ttu-id="c66fc-104">La palabra clave `protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="c66fc-104">The `protected` keyword is a member access modifier.</span></span>

> [!NOTE]
> <span data-ttu-id="c66fc-105">Esta página trata sobre el modificador de acceso `protected`.</span><span class="sxs-lookup"><span data-stu-id="c66fc-105">This page covers `protected` access.</span></span> <span data-ttu-id="c66fc-106">La palabra clave `protected` también forma parte de los modificadores de acceso [`protected internal`](protected-internal.md) y [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="c66fc-106">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="c66fc-107">Un miembro protegido es accesible dentro de su clase y por parte de instancias de clase derivadas.</span><span class="sxs-lookup"><span data-stu-id="c66fc-107">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="c66fc-108">Para obtener una comparación de `protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c66fc-108">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="c66fc-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c66fc-109">Example</span></span>

<span data-ttu-id="c66fc-110">Un miembro protegido de una clase base es accesible en una clase derivada únicamente si el acceso se produce a través del tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c66fc-110">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="c66fc-111">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="c66fc-111">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="c66fc-112">La instrucción `a.x = 10` genera un error porque se ha creado en el método estático Main y no en una instancia de clase B.</span><span class="sxs-lookup"><span data-stu-id="c66fc-112">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="c66fc-113">Los miembros de estructura no se pueden proteger porque la estructura no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="c66fc-113">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="c66fc-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c66fc-114">Example</span></span>

<span data-ttu-id="c66fc-115">En este ejemplo, la clase `DerivedPoint` se deriva de `Point`.</span><span class="sxs-lookup"><span data-stu-id="c66fc-115">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="c66fc-116">Por lo tanto, puede acceder a los miembros protegidos de la clase base directamente desde la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c66fc-116">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="c66fc-117">Si cambia los niveles de acceso de `x` y `y` a [private](private.md), el compilador genera los mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="c66fc-117">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="c66fc-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c66fc-118">C# language specification</span></span>  

<span data-ttu-id="c66fc-119">Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c66fc-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c66fc-120">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c66fc-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c66fc-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c66fc-121">See also</span></span>

- [<span data-ttu-id="c66fc-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c66fc-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c66fc-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c66fc-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c66fc-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="c66fc-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c66fc-125">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="c66fc-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="c66fc-126">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c66fc-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="c66fc-127">Modificadores</span><span class="sxs-lookup"><span data-stu-id="c66fc-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="c66fc-128">public</span><span class="sxs-lookup"><span data-stu-id="c66fc-128">public</span></span>](public.md)
- [<span data-ttu-id="c66fc-129">private</span><span class="sxs-lookup"><span data-stu-id="c66fc-129">private</span></span>](private.md)
- [<span data-ttu-id="c66fc-130">internal</span><span class="sxs-lookup"><span data-stu-id="c66fc-130">internal</span></span>](internal.md)
- <span data-ttu-id="c66fc-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="c66fc-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
