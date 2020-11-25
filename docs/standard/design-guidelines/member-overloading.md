---
title: Sobrecarga de miembro
ms.date: 10/22/2008
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: fe8bf23a04e6684564d3d7e287c2a009e0817732
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706637"
---
# <a name="member-overloading"></a><span data-ttu-id="5506d-102">Sobrecarga de miembro</span><span class="sxs-lookup"><span data-stu-id="5506d-102">Member Overloading</span></span>

<span data-ttu-id="5506d-103">La sobrecarga de miembros implica la creación de dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="5506d-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="5506d-104">Por ejemplo, en el siguiente caso, el `WriteLine` método está sobrecargado:</span><span class="sxs-lookup"><span data-stu-id="5506d-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 <span data-ttu-id="5506d-105">Dado que solo los métodos, los constructores y las propiedades indizadas pueden tener parámetros, solo esos miembros se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="5506d-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>

 <span data-ttu-id="5506d-106">La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, la productividad y la legibilidad de las bibliotecas reutilizables.</span><span class="sxs-lookup"><span data-stu-id="5506d-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="5506d-107">La sobrecarga en el número de parámetros permite proporcionar versiones más sencillas de constructores y métodos.</span><span class="sxs-lookup"><span data-stu-id="5506d-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="5506d-108">La sobrecarga en el tipo de parámetro permite usar el mismo nombre de miembro para los miembros que realizan operaciones idénticas en un conjunto seleccionado de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5506d-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>

 <span data-ttu-id="5506d-109">✔️ intente usar nombres de parámetro descriptivos para indicar el valor predeterminado usado por las sobrecargas más cortas.</span><span class="sxs-lookup"><span data-stu-id="5506d-109">✔️ DO try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>

 <span data-ttu-id="5506d-110">❌ Evite los nombres de parámetro que varían arbitrariamente en las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="5506d-110">❌ AVOID arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="5506d-111">Si un parámetro de una sobrecarga representa la misma entrada que un parámetro en otra sobrecarga, los parámetros deben tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="5506d-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>

 <span data-ttu-id="5506d-112">❌ Evite ser incoherentes en el orden de los parámetros en los miembros sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="5506d-112">❌ AVOID being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="5506d-113">Los parámetros con el mismo nombre deben aparecer en la misma posición en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="5506d-113">Parameters with the same name should appear in the same position in all overloads.</span></span>

 <span data-ttu-id="5506d-114">✔️ hacer solo la sobrecarga más larga virtual (si se requiere extensibilidad).</span><span class="sxs-lookup"><span data-stu-id="5506d-114">✔️ DO make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="5506d-115">Las sobrecargas más cortas simplemente deben llamar a a través de una sobrecarga más larga.</span><span class="sxs-lookup"><span data-stu-id="5506d-115">Shorter overloads should simply call through to a longer overload.</span></span>

 <span data-ttu-id="5506d-116">❌ No use `ref` `out` los modificadores o para sobrecargar los miembros.</span><span class="sxs-lookup"><span data-stu-id="5506d-116">❌ DO NOT use `ref` or `out` modifiers to overload members.</span></span>

 <span data-ttu-id="5506d-117">Algunos lenguajes no pueden resolver llamadas a sobrecargas como esta.</span><span class="sxs-lookup"><span data-stu-id="5506d-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="5506d-118">Además, estas sobrecargas suelen tener una semántica completamente diferente y probablemente no deberían ser sobrecargas, sino dos métodos independientes.</span><span class="sxs-lookup"><span data-stu-id="5506d-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>

 <span data-ttu-id="5506d-119">❌ NO tener sobrecargas con parámetros en la misma posición y tipos similares con semántica diferente.</span><span class="sxs-lookup"><span data-stu-id="5506d-119">❌ DO NOT have overloads with parameters at the same position and similar types yet with different semantics.</span></span>

 <span data-ttu-id="5506d-120">✔️ permitir `null` que se pasen los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="5506d-120">✔️ DO  allow `null` to be passed for optional arguments.</span></span>

 <span data-ttu-id="5506d-121">✔️ usar la sobrecarga de miembros en lugar de definir miembros con argumentos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5506d-121">✔️ DO use member overloading rather than defining members with default arguments.</span></span>

 <span data-ttu-id="5506d-122">Los argumentos predeterminados no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="5506d-122">Default arguments are not CLS compliant.</span></span>

 <span data-ttu-id="5506d-123">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="5506d-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5506d-124">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="5506d-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5506d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5506d-125">See also</span></span>

- [<span data-ttu-id="5506d-126">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="5506d-126">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="5506d-127">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="5506d-127">Framework Design Guidelines</span></span>](index.md)
