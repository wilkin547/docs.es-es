---
title: Diseño de clases estáticas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709067"
---
# <a name="static-class-design"></a><span data-ttu-id="757e4-102">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="757e4-102">Static Class Design</span></span>
<span data-ttu-id="757e4-103">Una clase estática se define como una clase que solo contiene miembros estáticos (por supuesto, además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado).</span><span class="sxs-lookup"><span data-stu-id="757e4-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="757e4-104">Algunos lenguajes proporcionan compatibilidad integrada con las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="757e4-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="757e4-105">En C# 2,0 y versiones posteriores, cuando una clase se declara como estática, es Sealed, abstract, y ningún miembro de instancia se puede invalidar o declarar.</span><span class="sxs-lookup"><span data-stu-id="757e4-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="757e4-106">Las clases estáticas son un compromiso entre el diseño y la simplicidad orientados a objetos puros.</span><span class="sxs-lookup"><span data-stu-id="757e4-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="757e4-107">Normalmente se utilizan para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), a los titulares de métodos de extensión o a la funcionalidad para la que no se garantiza un contenedor orientado a objetos completo (como <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="757e4-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="757e4-108">**✓ DO** usan clases estáticas con moderación.</span><span class="sxs-lookup"><span data-stu-id="757e4-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="757e4-109">Las clases estáticas solo se deben usar como clases de soporte para el núcleo orientado a objetos del marco.</span><span class="sxs-lookup"><span data-stu-id="757e4-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="757e4-110">**X DO NOT** tratar las clases estáticas como un depósito varios.</span><span class="sxs-lookup"><span data-stu-id="757e4-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="757e4-111">**X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="757e4-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="757e4-112">**✓ DO** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="757e4-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="757e4-113">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="757e4-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="757e4-114">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="757e4-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757e4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="757e4-115">See also</span></span>

- [<span data-ttu-id="757e4-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="757e4-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="757e4-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="757e4-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
