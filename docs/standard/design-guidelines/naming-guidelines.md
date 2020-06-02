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
ms.openlocfilehash: 1b137be60f4c8c1c7cf1fa1f807841d4bc209089
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290180"
---
# <a name="naming-guidelines"></a><span data-ttu-id="f2120-102">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="f2120-102">Naming Guidelines</span></span>
<span data-ttu-id="f2120-103">Seguir un conjunto coherente de convenciones de nomenclatura en el desarrollo de un marco de trabajo puede ser una contribución importante a la facilidad de uso del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2120-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="f2120-104">Permite que muchos desarrolladores usen el marco en proyectos ampliamente separados.</span><span class="sxs-lookup"><span data-stu-id="f2120-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="f2120-105">Además de la coherencia del formulario, los nombres de los elementos del marco deben entenderse fácilmente y deben transmitir la función de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f2120-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="f2120-106">El objetivo de este capítulo es proporcionar un conjunto coherente de convenciones de nomenclatura que dan lugar a los nombres que tienen sentido inmediato para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="f2120-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="f2120-107">Aunque adoptar estas convenciones de nomenclatura como directrices generales de desarrollo de código daría lugar a nombres más coherentes en todo el código, solo es necesario aplicarlos a las API que están expuestas públicamente (tipos y miembros públicos o protegidos e interfaces implementadas explícitamente).</span><span class="sxs-lookup"><span data-stu-id="f2120-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2120-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f2120-108">In This Section</span></span>  
 [<span data-ttu-id="f2120-109">Convenciones de capitalización</span><span class="sxs-lookup"><span data-stu-id="f2120-109">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="f2120-110">Convenciones generales de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="f2120-110">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="f2120-111">Nombres de ensamblados y dll</span><span class="sxs-lookup"><span data-stu-id="f2120-111">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="f2120-112">Nombres de los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="f2120-112">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="f2120-113">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="f2120-113">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="f2120-114">Nombres de miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="f2120-114">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="f2120-115">Nomenclatura de parámetros</span><span class="sxs-lookup"><span data-stu-id="f2120-115">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="f2120-116">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="f2120-116">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="f2120-117">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="f2120-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f2120-118">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="f2120-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2120-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2120-119">See also</span></span>

- [<span data-ttu-id="f2120-120">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="f2120-120">Framework Design Guidelines</span></span>](index.md)
