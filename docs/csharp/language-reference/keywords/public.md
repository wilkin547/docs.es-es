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
ms.openlocfilehash: 90c1d2a1d9efcdf57f914f4318bf7a743d3f37ec
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938473"
---
# <a name="public-c-reference"></a><span data-ttu-id="973c5-103">public (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="973c5-103">public (C# Reference)</span></span>

<span data-ttu-id="973c5-104">La palabra clave `public` es un modificador de acceso para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="973c5-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="973c5-105">El acceso público es el nivel de acceso más permisivo.</span><span class="sxs-lookup"><span data-stu-id="973c5-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="973c5-106">No hay ninguna restricción para el acceso a miembros públicos, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="973c5-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="973c5-107">Vea [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](accessibility-levels.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="973c5-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="973c5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="973c5-108">Example</span></span>

<span data-ttu-id="973c5-109">En el ejemplo siguiente, se declaran dos clases, `PointTest` y `Program`.</span><span class="sxs-lookup"><span data-stu-id="973c5-109">In the following example, two classes are declared, `PointTest` and `Program`.</span></span> <span data-ttu-id="973c5-110">Se obtiene acceso a los miembros públicos `x` e `y` de `PointTest` directamente desde `Program`.</span><span class="sxs-lookup"><span data-stu-id="973c5-110">The public members `x` and `y` of `PointTest` are accessed directly from `Program`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="973c5-111">Si cambia el nivel de acceso `public` a [private](private.md) o [protected](protected.md), obtendrá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="973c5-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="973c5-112">'PointTest.y' no es accesible debido a su nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="973c5-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="973c5-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="973c5-113">C# language specification</span></span>  

<span data-ttu-id="973c5-114">Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="973c5-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="973c5-115">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="973c5-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="973c5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="973c5-116">See also</span></span>

- [<span data-ttu-id="973c5-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="973c5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="973c5-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="973c5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="973c5-119">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="973c5-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="973c5-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="973c5-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="973c5-121">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="973c5-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="973c5-122">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="973c5-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="973c5-123">Modificadores</span><span class="sxs-lookup"><span data-stu-id="973c5-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="973c5-124">private</span><span class="sxs-lookup"><span data-stu-id="973c5-124">private</span></span>](private.md)
- [<span data-ttu-id="973c5-125">protected</span><span class="sxs-lookup"><span data-stu-id="973c5-125">protected</span></span>](protected.md)
- [<span data-ttu-id="973c5-126">internal</span><span class="sxs-lookup"><span data-stu-id="973c5-126">internal</span></span>](internal.md)
