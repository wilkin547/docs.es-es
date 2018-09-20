---
title: Diseño de clases estáticas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471318"
---
# <a name="static-class-design"></a><span data-ttu-id="6bcf2-102">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="6bcf2-102">Static Class Design</span></span>
<span data-ttu-id="6bcf2-103">Se define una clase estática como una clase que contiene sólo miembros estáticos (por supuesto además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y, posiblemente, un constructor privado).</span><span class="sxs-lookup"><span data-stu-id="6bcf2-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="6bcf2-104">Algunos lenguajes ofrecen compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="6bcf2-105">En C# 2.0 y versiones posteriores, cuando una clase se declara como estática, está sellada y abstracta y se puede invalidar o declarado ningún miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="6bcf2-106">Las clases estáticas son un compromiso entre el diseño orientado a objetos puro y simplicidad.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="6bcf2-107">Se suelen usar para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), los propietarios de los métodos de extensión o la funcionalidad para el que se no fundamentado un contenedor completa orientada a objetos (como <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="6bcf2-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="6bcf2-108">**✓ DO** usan clases estáticas con moderación.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="6bcf2-109">Las clases estáticas deben usarse solo como clases auxiliares para las principales orientada a objetos de framework.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="6bcf2-110">**X DO NOT** tratar las clases estáticas como un depósito varios.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="6bcf2-111">**X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="6bcf2-112">**✓ DO** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="6bcf2-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="6bcf2-113">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6bcf2-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6bcf2-114">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="6bcf2-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcf2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bcf2-115">See also</span></span>

- [<span data-ttu-id="6bcf2-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="6bcf2-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="6bcf2-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6bcf2-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
