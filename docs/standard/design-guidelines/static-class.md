---
description: 'Más información acerca de: Diseño de clases estáticas'
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
ms.openlocfilehash: 16db470ab0975a5545617c9c5471d6ac157e688b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782473"
---
# <a name="static-class-design"></a><span data-ttu-id="f69b1-103">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="f69b1-103">Static Class Design</span></span>

<span data-ttu-id="f69b1-104">Una clase estática se define como una clase que solo contiene miembros estáticos (por supuesto, además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado).</span><span class="sxs-lookup"><span data-stu-id="f69b1-104">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="f69b1-105">Algunos lenguajes proporcionan compatibilidad integrada con las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="f69b1-105">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="f69b1-106">En C# 2.0 y versiones posteriores, cuando una clase se declara como estática, está sellada, es abstracta y ningún miembro de instancia se puede invalidar ni declarar.</span><span class="sxs-lookup"><span data-stu-id="f69b1-106">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="f69b1-107">Las clases estáticas son un compromiso entre el diseño y la simplicidad orientados a objetos puros.</span><span class="sxs-lookup"><span data-stu-id="f69b1-107">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="f69b1-108">Normalmente se utilizan para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), contenedores de métodos de extensión o una funcionalidad para la que no se garantiza un contenedor orientado a objetos completo (como <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="f69b1-108">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="f69b1-109">✔️ USE las clases estáticas con moderación.</span><span class="sxs-lookup"><span data-stu-id="f69b1-109">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="f69b1-110">Las clases estáticas solo se deben usar como clases de compatibilidad para el núcleo orientado a objetos del marco.</span><span class="sxs-lookup"><span data-stu-id="f69b1-110">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="f69b1-111">❌ NO trate las clases estáticas como un cubo diferente.</span><span class="sxs-lookup"><span data-stu-id="f69b1-111">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="f69b1-112">❌ NO declare ni invalide los miembros de instancia en las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="f69b1-112">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="f69b1-113">✔️ DECLARE las clases estáticas como selladas y abstractas, y agregue un constructor de instancia privado si su lenguaje de programación no tiene compatibilidad integrada con las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="f69b1-113">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="f69b1-114">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="f69b1-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f69b1-115">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="f69b1-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f69b1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f69b1-116">See also</span></span>

- [<span data-ttu-id="f69b1-117">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="f69b1-117">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="f69b1-118">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f69b1-118">Framework Design Guidelines</span></span>](index.md)
