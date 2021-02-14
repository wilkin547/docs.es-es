---
description: 'Más información acerca de: Sobrecarga de miembro'
title: Sobrecarga de miembro
ms.date: 10/22/2008
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: d3a545bfec552686e55c9f713d58784497946819
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641959"
---
# <a name="member-overloading"></a><span data-ttu-id="1567b-103">Sobrecarga de miembro</span><span class="sxs-lookup"><span data-stu-id="1567b-103">Member Overloading</span></span>

<span data-ttu-id="1567b-104">La sobrecarga de miembro implica la creación de dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1567b-104">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="1567b-105">Por ejemplo, en lo siguiente, el método `WriteLine`, se sobrecarga:</span><span class="sxs-lookup"><span data-stu-id="1567b-105">For example, in the following, the `WriteLine` method is overloaded:</span></span>

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 <span data-ttu-id="1567b-106">Dado que solo los métodos, los constructores y las propiedades indizadas pueden tener parámetros, solo esos miembros se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="1567b-106">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>

 <span data-ttu-id="1567b-107">La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, la productividad y la legibilidad de las bibliotecas reutilizables.</span><span class="sxs-lookup"><span data-stu-id="1567b-107">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="1567b-108">La sobrecarga en el número de parámetros permite proporcionar versiones más sencillas de constructores y métodos.</span><span class="sxs-lookup"><span data-stu-id="1567b-108">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="1567b-109">La sobrecarga en el tipo de parámetro permite usar el mismo nombre de miembro para los miembros que realizan operaciones idénticas en un conjunto seleccionado de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="1567b-109">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>

 <span data-ttu-id="1567b-110">✔️ DEBE intentar usar nombres de parámetro descriptivos para indicar el valor predeterminado usado por las sobrecargas más cortas.</span><span class="sxs-lookup"><span data-stu-id="1567b-110">✔️ DO try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>

 <span data-ttu-id="1567b-111">❌ EVITE los nombres de parámetro que varían arbitrariamente en las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="1567b-111">❌ AVOID arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="1567b-112">Si un parámetro de una sobrecarga representa la misma entrada que un parámetro de otra sobrecarga, los parámetros deben tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1567b-112">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>

 <span data-ttu-id="1567b-113">❌ EVITE ser incoherente en el orden de los parámetros en los miembros sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="1567b-113">❌ AVOID being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="1567b-114">Los parámetros con el mismo nombre deben aparecer en la misma posición en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="1567b-114">Parameters with the same name should appear in the same position in all overloads.</span></span>

 <span data-ttu-id="1567b-115">✔️ DEBE convertir en virtual solo la sobrecarga más larga (si se requiere extensibilidad).</span><span class="sxs-lookup"><span data-stu-id="1567b-115">✔️ DO make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="1567b-116">Las sobrecargas más cortas simplemente deben llamar a través de una sobrecarga más larga.</span><span class="sxs-lookup"><span data-stu-id="1567b-116">Shorter overloads should simply call through to a longer overload.</span></span>

 <span data-ttu-id="1567b-117">❌ NO utilice los modificadores `ref` o `out` para sobrecargar los miembros.</span><span class="sxs-lookup"><span data-stu-id="1567b-117">❌ DO NOT use `ref` or `out` modifiers to overload members.</span></span>

 <span data-ttu-id="1567b-118">Algunos lenguajes no pueden resolver llamadas a sobrecargas como esta.</span><span class="sxs-lookup"><span data-stu-id="1567b-118">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="1567b-119">Además, estas sobrecargas suelen tener una semántica completamente diferente y probablemente no deberían ser sobrecargas, sino dos métodos independientes.</span><span class="sxs-lookup"><span data-stu-id="1567b-119">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>

 <span data-ttu-id="1567b-120">❌ NO tener sobrecargas con parámetros en la misma posición y tipos similares con semántica diferente.</span><span class="sxs-lookup"><span data-stu-id="1567b-120">❌ DO NOT have overloads with parameters at the same position and similar types yet with different semantics.</span></span>

 <span data-ttu-id="1567b-121">✔️ DEBE permitir que `null` se pase para los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="1567b-121">✔️ DO  allow `null` to be passed for optional arguments.</span></span>

 <span data-ttu-id="1567b-122">✔️ DEBE usar la sobrecarga de miembros en lugar de definir miembros con argumentos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1567b-122">✔️ DO use member overloading rather than defining members with default arguments.</span></span>

 <span data-ttu-id="1567b-123">Los argumentos predeterminados no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="1567b-123">Default arguments are not CLS compliant.</span></span>

 <span data-ttu-id="1567b-124">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1567b-124">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1567b-125">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1567b-125">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1567b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1567b-126">See also</span></span>

- [<span data-ttu-id="1567b-127">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="1567b-127">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="1567b-128">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1567b-128">Framework Design Guidelines</span></span>](index.md)
