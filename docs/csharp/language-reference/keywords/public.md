---
title: Palabra clave public (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: b2e09bdb16d6128d69a3eb33cf2cffd4cba60376
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "43518191"
---
# <a name="public-c-reference"></a><span data-ttu-id="a5693-102">public (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a5693-102">public (C# Reference)</span></span>

<span data-ttu-id="a5693-103">La palabra clave `public` es un modificador de acceso para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="a5693-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="a5693-104">El acceso público es el nivel de acceso más permisivo.</span><span class="sxs-lookup"><span data-stu-id="a5693-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="a5693-105">No hay ninguna restricción para el acceso a miembros públicos, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5693-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="a5693-106">Vea [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](accessibility-levels.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5693-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="a5693-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5693-107">Example</span></span>

<span data-ttu-id="a5693-108">En el ejemplo siguiente, se declaran dos clases, `PointTest` y `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="a5693-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="a5693-109">Se obtiene acceso a los miembros públicos `x` e `y` de `PointTest` directamente desde `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="a5693-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="a5693-110">Si cambia el nivel de acceso `public` a [private](private.md) o [protected](protected.md), obtendrá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="a5693-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="a5693-111">'PointTest.y' no es accesible debido a su nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="a5693-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a5693-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a5693-112">C# language specification</span></span>  

<span data-ttu-id="a5693-113">Para obtener más información, vea la sección [Accesibilidad declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5693-113">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="a5693-114">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="a5693-114">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5693-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5693-115">See also</span></span>

- [<span data-ttu-id="a5693-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a5693-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a5693-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a5693-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a5693-118">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="a5693-118">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="a5693-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a5693-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a5693-120">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="a5693-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a5693-121">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="a5693-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a5693-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="a5693-122">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="a5693-123">private</span><span class="sxs-lookup"><span data-stu-id="a5693-123">private</span></span>](private.md)
- [<span data-ttu-id="a5693-124">protected</span><span class="sxs-lookup"><span data-stu-id="a5693-124">protected</span></span>](protected.md)
- [<span data-ttu-id="a5693-125">internal</span><span class="sxs-lookup"><span data-stu-id="a5693-125">internal</span></span>](internal.md)