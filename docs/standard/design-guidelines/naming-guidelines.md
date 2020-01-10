---
title: Instrucciones de nomenclatura
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: ad98c0f3b02bdc81e6348493b4e0a02f9cb20ed4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709197"
---
# <a name="naming-guidelines"></a><span data-ttu-id="91f95-102">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="91f95-102">Naming Guidelines</span></span>
<span data-ttu-id="91f95-103">Seguir un conjunto coherente de convenciones de nomenclatura en el desarrollo de un marco de trabajo puede ser una contribución importante a la facilidad de uso del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91f95-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="91f95-104">Permite que muchos desarrolladores usen el marco en proyectos ampliamente separados.</span><span class="sxs-lookup"><span data-stu-id="91f95-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="91f95-105">Además de la coherencia del formulario, los nombres de los elementos del marco deben entenderse fácilmente y deben transmitir la función de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="91f95-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="91f95-106">El objetivo de este capítulo es proporcionar un conjunto coherente de convenciones de nomenclatura que dan lugar a los nombres que tienen sentido inmediato para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="91f95-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="91f95-107">Aunque adoptar estas convenciones de nomenclatura como directrices generales de desarrollo de código daría lugar a nombres más coherentes en todo el código, solo es necesario aplicarlos a las API que están expuestas públicamente (tipos y miembros públicos o protegidos). interfaces implementadas explícitamente).</span><span class="sxs-lookup"><span data-stu-id="91f95-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91f95-108">Esta sección</span><span class="sxs-lookup"><span data-stu-id="91f95-108">In This Section</span></span>  
 [<span data-ttu-id="91f95-109">Convenciones sobre el uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="91f95-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="91f95-110">Convenciones generales de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="91f95-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="91f95-111">Nombres de ensamblados y bibliotecas DLL</span><span class="sxs-lookup"><span data-stu-id="91f95-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="91f95-112">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="91f95-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="91f95-113">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="91f95-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="91f95-114">Nombres de miembros de tipos</span><span class="sxs-lookup"><span data-stu-id="91f95-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="91f95-115">Asignación de nombres a parámetros</span><span class="sxs-lookup"><span data-stu-id="91f95-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="91f95-116">Asignación de nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="91f95-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="91f95-117">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="91f95-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="91f95-118">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="91f95-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f95-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f95-119">See also</span></span>

- [<span data-ttu-id="91f95-120">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="91f95-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
