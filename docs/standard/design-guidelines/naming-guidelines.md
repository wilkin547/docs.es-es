---
title: Instrucciones de nomenclatura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 713a11f822dd30e77e6442c0bb082a40755b1832
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="naming-guidelines"></a><span data-ttu-id="b7d9e-102">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b7d9e-102">Naming Guidelines</span></span>
<span data-ttu-id="b7d9e-103">Después de un conjunto coherente de las convenciones de nomenclatura en el desarrollo de un marco de trabajo pueden ser una contribución importante para facilidad de uso del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b7d9e-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="b7d9e-104">Permite al marco de trabajo se utilizan numerosos desarrolladores en proyectos ampliamente separados.</span><span class="sxs-lookup"><span data-stu-id="b7d9e-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="b7d9e-105">Más allá de la coherencia del formulario, los nombres de elementos de marco deben entenderse fácilmente y deben transmitir la función de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="b7d9e-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="b7d9e-106">El objetivo de este capítulo es proporcionar un conjunto coherente de las convenciones de nomenclatura que se crean nombres que tengan sentido inmediata a los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="b7d9e-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="b7d9e-107">Aunque el uso de estas convenciones de nomenclatura según las directrices de desarrollo general del código, se crearán una nomenclatura más coherente en todo el código, se requiere solo para aplicarlas a las API que se exponen públicamente (públicos o protegidos tipos y miembros, y se implementa explícitamente interfaces).</span><span class="sxs-lookup"><span data-stu-id="b7d9e-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7d9e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7d9e-108">In This Section</span></span>  
 [<span data-ttu-id="b7d9e-109">Convenciones sobre el uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="b7d9e-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="b7d9e-110">Convenciones generales de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b7d9e-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="b7d9e-111">Nombres de ensamblados y bibliotecas DLL</span><span class="sxs-lookup"><span data-stu-id="b7d9e-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="b7d9e-112">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="b7d9e-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="b7d9e-113">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="b7d9e-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="b7d9e-114">Nombres de miembros de tipos</span><span class="sxs-lookup"><span data-stu-id="b7d9e-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="b7d9e-115">Asignación de nombres a parámetros</span><span class="sxs-lookup"><span data-stu-id="b7d9e-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="b7d9e-116">Asignación de nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="b7d9e-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="b7d9e-117">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="b7d9e-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b7d9e-118">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b7d9e-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d9e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7d9e-119">See Also</span></span>  
 [<span data-ttu-id="b7d9e-120">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7d9e-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
