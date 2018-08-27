---
title: public (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 853f9c9ebe36345a897337d4e793d3c88059e068
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998732"
---
# <a name="public-c-reference"></a><span data-ttu-id="821ca-102">public (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="821ca-102">public (C# Reference)</span></span>
<span data-ttu-id="821ca-103">La palabra clave `public` es un modificador de acceso para tipos y miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="821ca-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="821ca-104">El acceso público es el nivel de acceso más permisivo.</span><span class="sxs-lookup"><span data-stu-id="821ca-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="821ca-105">No hay ninguna restricción para el acceso a miembros públicos, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="821ca-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="821ca-106">Vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="821ca-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="821ca-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="821ca-107">Example</span></span>  
 <span data-ttu-id="821ca-108">En el ejemplo siguiente, se declaran dos clases, `PointTest` y `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="821ca-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="821ca-109">Se obtiene acceso a los miembros públicos `x` e `y` de `PointTest` directamente desde `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="821ca-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 <span data-ttu-id="821ca-110">Si cambia el nivel de acceso `public` a [private](../../../csharp/language-reference/keywords/private.md) o [protected](../../../csharp/language-reference/keywords/protected.md), obtendrá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="821ca-110">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="821ca-111">'PointTest.y' no es accesible debido a su nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="821ca-111">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="821ca-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="821ca-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="821ca-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="821ca-113">See Also</span></span>

- [<span data-ttu-id="821ca-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="821ca-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="821ca-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="821ca-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="821ca-116">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="821ca-116">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="821ca-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="821ca-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="821ca-118">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="821ca-118">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="821ca-119">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="821ca-119">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="821ca-120">Modificadores</span><span class="sxs-lookup"><span data-stu-id="821ca-120">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="821ca-121">private</span><span class="sxs-lookup"><span data-stu-id="821ca-121">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="821ca-122">protected</span><span class="sxs-lookup"><span data-stu-id="821ca-122">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
- [<span data-ttu-id="821ca-123">internal</span><span class="sxs-lookup"><span data-stu-id="821ca-123">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
