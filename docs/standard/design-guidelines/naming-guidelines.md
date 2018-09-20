---
title: Instrucciones de nomenclatura
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70888e068782add5ebe5ae1c7da3bdee842faea8
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45529073"
---
# <a name="naming-guidelines"></a><span data-ttu-id="92324-102">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="92324-102">Naming Guidelines</span></span>
<span data-ttu-id="92324-103">Seguir un conjunto coherente de convenciones de nomenclatura en el desarrollo de un marco de trabajo puede ser una contribución importante a la facilidad de uso de .NET framework.</span><span class="sxs-lookup"><span data-stu-id="92324-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="92324-104">Permite que el marco de trabajo que va a utilizar muchos desarrolladores en proyectos separados ampliamente.</span><span class="sxs-lookup"><span data-stu-id="92324-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="92324-105">Más allá de la coherencia del formulario, los nombres de elementos de marco se deben entender fácilmente y deben transmitir la función de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="92324-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="92324-106">El objetivo de este capítulo es proporcionar un conjunto coherente de convenciones de nomenclatura que da como resultado nombres que tengan sentido inmediata a los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="92324-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="92324-107">Aunque adoptar estas convenciones de nomenclatura que daría lugar a las instrucciones de desarrollo de código general de nomenclatura más coherente en todo el código, debe sólo para aplicarlas a las API que se exponen públicamente (public o protected tipos y miembros, y explícitamente interfaces implementadas).</span><span class="sxs-lookup"><span data-stu-id="92324-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92324-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="92324-108">In This Section</span></span>  
 [<span data-ttu-id="92324-109">Convenciones sobre el uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="92324-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="92324-110">Convenciones generales de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="92324-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="92324-111">Nombres de ensamblados y bibliotecas DLL</span><span class="sxs-lookup"><span data-stu-id="92324-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="92324-112">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="92324-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="92324-113">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="92324-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="92324-114">Nombres de miembros de tipos</span><span class="sxs-lookup"><span data-stu-id="92324-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="92324-115">Asignación de nombres a parámetros</span><span class="sxs-lookup"><span data-stu-id="92324-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="92324-116">Asignación de nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="92324-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="92324-117">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="92324-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="92324-118">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="92324-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92324-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="92324-119">See also</span></span>

- [<span data-ttu-id="92324-120">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="92324-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
