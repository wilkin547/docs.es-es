---
title: Palabra clave public (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 84a3bc49b6eea047d518edc01dab7f2301854b6a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484162"
---
# <a name="public-c-reference"></a><span data-ttu-id="dc52d-102">public (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="dc52d-102">public (C# Reference)</span></span>

<span data-ttu-id="dc52d-103">La palabra clave `public` es un modificador de acceso para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="dc52d-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="dc52d-104">El acceso público es el nivel de acceso más permisivo.</span><span class="sxs-lookup"><span data-stu-id="dc52d-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="dc52d-105">No hay ninguna restricción para el acceso a miembros públicos, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dc52d-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="dc52d-106">Vea [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](accessibility-levels.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dc52d-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="dc52d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc52d-107">Example</span></span>

<span data-ttu-id="dc52d-108">En el ejemplo siguiente, se declaran dos clases, `PointTest` y `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="dc52d-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="dc52d-109">Se obtiene acceso a los miembros públicos `x` e `y` de `PointTest` directamente desde `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="dc52d-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="dc52d-110">Si cambia el nivel de acceso `public` a [private](private.md) o [protected](protected.md), obtendrá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="dc52d-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="dc52d-111">'PointTest.y' no es accesible debido a su nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="dc52d-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dc52d-112">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dc52d-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dc52d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc52d-113">See also</span></span>

- [<span data-ttu-id="dc52d-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="dc52d-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dc52d-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dc52d-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc52d-116">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="dc52d-116">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="dc52d-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="dc52d-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dc52d-118">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="dc52d-118">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="dc52d-119">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="dc52d-119">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="dc52d-120">Modificadores</span><span class="sxs-lookup"><span data-stu-id="dc52d-120">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="dc52d-121">private</span><span class="sxs-lookup"><span data-stu-id="dc52d-121">private</span></span>](private.md)
- [<span data-ttu-id="dc52d-122">protected</span><span class="sxs-lookup"><span data-stu-id="dc52d-122">protected</span></span>](protected.md)
- [<span data-ttu-id="dc52d-123">internal</span><span class="sxs-lookup"><span data-stu-id="dc52d-123">internal</span></span>](internal.md)