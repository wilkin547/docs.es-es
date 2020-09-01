---
description: 'Palabra clave private: Referencia de C#'
title: 'Palabra clave private: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: e6f40712fd2cca6d7b1f64760f1c6c5dd5c71370
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139403"
---
# <a name="private-c-reference"></a><span data-ttu-id="b77e0-103">private (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b77e0-103">private (C# Reference)</span></span>

<span data-ttu-id="b77e0-104">La palabra clave `private` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="b77e0-104">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="b77e0-105">Esta página trata sobre el modificador de acceso `private`.</span><span class="sxs-lookup"><span data-stu-id="b77e0-105">This page covers `private` access.</span></span> <span data-ttu-id="b77e0-106">La palabra clave `private` también forma parte del modificador de acceso [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="b77e0-106">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="b77e0-107">El acceso privado es el nivel de acceso menos permisivo.</span><span class="sxs-lookup"><span data-stu-id="b77e0-107">Private access is the least permissive access level.</span></span> <span data-ttu-id="b77e0-108">Los miembros privados solo son accesibles dentro del cuerpo de la clase o el struct en el que se declaran, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b77e0-108">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="b77e0-109">Los tipos anidados en el mismo cuerpo también pueden tener acceso a los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="b77e0-109">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="b77e0-110">Hacer referencia a un miembro privado fuera de la clase o el struct en el que se declara es un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b77e0-110">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="b77e0-111">Para obtener una comparación de `private` con los demás modificadores de acceso, vea [Niveles de accesibilidad](accessibility-levels.md) y [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="b77e0-111">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="b77e0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b77e0-112">Example</span></span>

<span data-ttu-id="b77e0-113">En este ejemplo, la clase `Employee` contiene dos miembros de datos privados, `name` y `salary`.</span><span class="sxs-lookup"><span data-stu-id="b77e0-113">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="b77e0-114">Como miembros privados, solo pueden tener acceso a ellos los métodos de miembro.</span><span class="sxs-lookup"><span data-stu-id="b77e0-114">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="b77e0-115">Los métodos públicos denominados `GetName` y `Salary` se agregan para permitir un acceso controlado a los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="b77e0-115">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="b77e0-116">Se tiene acceso al miembro `name` a través de un método público, mientras que se tiene acceso al miembro `salary` a través de una propiedad pública de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b77e0-116">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="b77e0-117">(Para obtener más información, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md)).</span><span class="sxs-lookup"><span data-stu-id="b77e0-117">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="b77e0-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b77e0-118">C# language specification</span></span>  

<span data-ttu-id="b77e0-119">Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="b77e0-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b77e0-120">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="b77e0-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b77e0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b77e0-121">See also</span></span>

- [<span data-ttu-id="b77e0-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b77e0-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b77e0-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b77e0-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b77e0-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="b77e0-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b77e0-125">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="b77e0-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="b77e0-126">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="b77e0-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="b77e0-127">Modificadores</span><span class="sxs-lookup"><span data-stu-id="b77e0-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b77e0-128">public</span><span class="sxs-lookup"><span data-stu-id="b77e0-128">public</span></span>](public.md)
- [<span data-ttu-id="b77e0-129">protected</span><span class="sxs-lookup"><span data-stu-id="b77e0-129">protected</span></span>](protected.md)
- [<span data-ttu-id="b77e0-130">internal</span><span class="sxs-lookup"><span data-stu-id="b77e0-130">internal</span></span>](internal.md)
