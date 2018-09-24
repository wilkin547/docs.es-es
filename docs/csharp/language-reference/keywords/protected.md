---
title: Palabra clave protected (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: f25e692430f876ec384971079d6d0aa2c97e967b
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577443"
---
# <a name="protected-c-reference"></a><span data-ttu-id="550a2-102">protected (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="550a2-102">protected (C# Reference)</span></span>

<span data-ttu-id="550a2-103">La palabra clave `protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="550a2-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="550a2-104">Esta página trata sobre el modificador de acceso `protected`.</span><span class="sxs-lookup"><span data-stu-id="550a2-104">This page covers `protected` access.</span></span> <span data-ttu-id="550a2-105">La palabra clave `protected` también forma parte de los modificadores de acceso [`protected internal`](protected-internal.md) y [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="550a2-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="550a2-106">Un miembro protegido es accesible dentro de su clase y por parte de instancias de clase derivadas.</span><span class="sxs-lookup"><span data-stu-id="550a2-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="550a2-107">Para obtener una comparación de `protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="550a2-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="550a2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="550a2-108">Example</span></span>

<span data-ttu-id="550a2-109">Un miembro protegido de una clase base es accesible en una clase derivada únicamente si el acceso se produce a través del tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="550a2-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="550a2-110">Por ejemplo, vea el siguiente segmento de código:</span><span class="sxs-lookup"><span data-stu-id="550a2-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="550a2-111">La instrucción `a.x = 10` genera un error porque se ha creado en el método estático Main y no en una instancia de clase B.</span><span class="sxs-lookup"><span data-stu-id="550a2-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="550a2-112">Los miembros de estructura no se pueden proteger porque la estructura no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="550a2-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="550a2-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="550a2-113">Example</span></span>

<span data-ttu-id="550a2-114">En este ejemplo, la clase `DerivedPoint` se deriva de `Point`.</span><span class="sxs-lookup"><span data-stu-id="550a2-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="550a2-115">Por lo tanto, puede acceder a los miembros protegidos de la clase base directamente desde la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="550a2-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="550a2-116">Si cambia los niveles de acceso de `x` y `y` a [private](private.md), el compilador genera los mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="550a2-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="550a2-117">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="550a2-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="550a2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="550a2-118">See also</span></span>

- [<span data-ttu-id="550a2-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="550a2-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="550a2-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="550a2-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="550a2-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="550a2-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="550a2-122">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="550a2-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="550a2-123">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="550a2-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="550a2-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="550a2-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="550a2-125">public</span><span class="sxs-lookup"><span data-stu-id="550a2-125">public</span></span>](public.md)
- [<span data-ttu-id="550a2-126">private</span><span class="sxs-lookup"><span data-stu-id="550a2-126">private</span></span>](private.md)
- [<span data-ttu-id="550a2-127">internal</span><span class="sxs-lookup"><span data-stu-id="550a2-127">internal</span></span>](internal.md)
- <span data-ttu-id="550a2-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100)) (Problemas de seguridad de palabras clave virtuales internas)</span><span class="sxs-lookup"><span data-stu-id="550a2-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>