---
title: Instrucciones de nomenclatura
description: En esta información general, obtenga información sobre las convenciones de nomenclatura que se usan en el desarrollo de .NET Framework. Vaya a artículos que cubran las mayúsculas y minúsculas, nombres generales y otras directrices.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: e82b6941d3ea0243f4ae16bc9d42ea8d1f1fccfb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820883"
---
# <a name="naming-guidelines"></a><span data-ttu-id="1f3ac-104">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1f3ac-104">Naming Guidelines</span></span>
<span data-ttu-id="1f3ac-105">Seguir un conjunto coherente de convenciones de nomenclatura en el desarrollo de un marco de trabajo puede ser una contribución importante a la facilidad de uso del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1f3ac-105">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="1f3ac-106">Permite que muchos desarrolladores usen el marco en proyectos ampliamente separados.</span><span class="sxs-lookup"><span data-stu-id="1f3ac-106">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="1f3ac-107">Además de la coherencia del formulario, los nombres de los elementos del marco deben entenderse fácilmente y deben transmitir la función de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="1f3ac-107">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="1f3ac-108">El objetivo de este capítulo es proporcionar un conjunto coherente de convenciones de nomenclatura que dan lugar a los nombres que tienen sentido inmediato para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="1f3ac-108">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="1f3ac-109">Aunque adoptar estas convenciones de nomenclatura como directrices generales de desarrollo de código daría lugar a nombres más coherentes en todo el código, solo es necesario aplicarlos a las API que están expuestas públicamente (tipos y miembros públicos o protegidos e interfaces implementadas explícitamente).</span><span class="sxs-lookup"><span data-stu-id="1f3ac-109">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f3ac-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f3ac-110">In This Section</span></span>  
 [<span data-ttu-id="1f3ac-111">Convenciones de capitalización</span><span class="sxs-lookup"><span data-stu-id="1f3ac-111">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="1f3ac-112">Convenciones generales de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1f3ac-112">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="1f3ac-113">Nombres de ensamblados y dll</span><span class="sxs-lookup"><span data-stu-id="1f3ac-113">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="1f3ac-114">Nombres de los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="1f3ac-114">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="1f3ac-115">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="1f3ac-115">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="1f3ac-116">Nombres de miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="1f3ac-116">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="1f3ac-117">Nomenclatura de parámetros</span><span class="sxs-lookup"><span data-stu-id="1f3ac-117">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="1f3ac-118">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="1f3ac-118">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="1f3ac-119">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1f3ac-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1f3ac-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1f3ac-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3ac-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f3ac-121">See also</span></span>

- [<span data-ttu-id="1f3ac-122">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="1f3ac-122">Framework Design Guidelines</span></span>](index.md)
