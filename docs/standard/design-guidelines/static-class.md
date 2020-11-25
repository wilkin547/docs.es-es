---
title: Diseño de clases estáticas
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 2ae541898435773ca51dbc425c09a533dbef4e9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730921"
---
# <a name="static-class-design"></a><span data-ttu-id="ed5c8-102">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="ed5c8-102">Static Class Design</span></span>

<span data-ttu-id="ed5c8-103">Una clase estática se define como una clase que solo contiene miembros estáticos (por supuesto, además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado).</span><span class="sxs-lookup"><span data-stu-id="ed5c8-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="ed5c8-104">Algunos lenguajes proporcionan compatibilidad integrada con las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="ed5c8-105">En C# 2,0 y versiones posteriores, cuando una clase se declara como estática, es Sealed, abstract, y no se pueden reemplazar o declarar miembros de instancia.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="ed5c8-106">Las clases estáticas son un compromiso entre el diseño y la simplicidad orientados a objetos puros.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="ed5c8-107">Normalmente se utilizan para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType> ), a los titulares de métodos de extensión o a la funcionalidad para la que no se garantiza un contenedor orientado a objetos completo (como <xref:System.Environment?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="ed5c8-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="ed5c8-108">✔️ usar las clases estáticas con moderación.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="ed5c8-109">Las clases estáticas solo se deben usar como clases de soporte para el núcleo orientado a objetos del marco.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="ed5c8-110">❌ No trate clases estáticas como un cubo misceláneo.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="ed5c8-111">❌ NO declare ni invalide miembros de instancia en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="ed5c8-112">✔️ declare las clases estáticas como Sealed, abstract y agregue un constructor de instancia privado si el lenguaje de programación no tiene compatibilidad integrada con las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="ed5c8-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="ed5c8-113">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="ed5c8-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ed5c8-114">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="ed5c8-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ed5c8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed5c8-115">See also</span></span>

- [<span data-ttu-id="ed5c8-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="ed5c8-116">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="ed5c8-117">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="ed5c8-117">Framework Design Guidelines</span></span>](index.md)
