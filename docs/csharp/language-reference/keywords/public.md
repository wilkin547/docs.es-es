---
description: 'Palabra clave public: Referencia de C#'
title: 'Palabra clave public: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 26edaf7538d11d082a4b8863228213c3ebc46937
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122347"
---
# <a name="public-c-reference"></a><span data-ttu-id="f40e5-103">public (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f40e5-103">public (C# Reference)</span></span>

<span data-ttu-id="f40e5-104">La palabra clave `public` es un modificador de acceso para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="f40e5-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="f40e5-105">El acceso público es el nivel de acceso más permisivo.</span><span class="sxs-lookup"><span data-stu-id="f40e5-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="f40e5-106">No hay ninguna restricción para el acceso a miembros públicos, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f40e5-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="f40e5-107">Vea [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](accessibility-levels.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f40e5-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="f40e5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f40e5-108">Example</span></span>

<span data-ttu-id="f40e5-109">En el ejemplo siguiente, se declaran dos clases, `PointTest` y `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="f40e5-109">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="f40e5-110">Se obtiene acceso a los miembros públicos `x` e `y` de `PointTest` directamente desde `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="f40e5-110">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="f40e5-111">Si cambia el nivel de acceso `public` a [private](private.md) o [protected](protected.md), obtendrá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="f40e5-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="f40e5-112">'PointTest.y' no es accesible debido a su nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="f40e5-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f40e5-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f40e5-113">C# language specification</span></span>  

<span data-ttu-id="f40e5-114">Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="f40e5-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="f40e5-115">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="f40e5-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="f40e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f40e5-116">See also</span></span>

- [<span data-ttu-id="f40e5-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f40e5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f40e5-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f40e5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f40e5-119">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="f40e5-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="f40e5-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f40e5-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f40e5-121">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="f40e5-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="f40e5-122">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="f40e5-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="f40e5-123">Modificadores</span><span class="sxs-lookup"><span data-stu-id="f40e5-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f40e5-124">private</span><span class="sxs-lookup"><span data-stu-id="f40e5-124">private</span></span>](private.md)
- [<span data-ttu-id="f40e5-125">protected</span><span class="sxs-lookup"><span data-stu-id="f40e5-125">protected</span></span>](protected.md)
- [<span data-ttu-id="f40e5-126">internal</span><span class="sxs-lookup"><span data-stu-id="f40e5-126">internal</span></span>](internal.md)
