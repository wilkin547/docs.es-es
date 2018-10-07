---
title: Miembros virtuales
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92b648e7886fb0214238e32eacae2870b470340
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847456"
---
# <a name="virtual-members"></a><span data-ttu-id="3db1a-102">Miembros virtuales</span><span class="sxs-lookup"><span data-stu-id="3db1a-102">Virtual Members</span></span>
<span data-ttu-id="3db1a-103">Pueden invalidar los miembros virtuales, lo que cambiará el comportamiento de la subclase.</span><span class="sxs-lookup"><span data-stu-id="3db1a-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="3db1a-104">Son muy similares a las devoluciones de llamada en cuanto a la extensibilidad que proporcionan, pero están mejores en términos de rendimiento de la ejecución y el consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="3db1a-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="3db1a-105">Además, los miembros virtuales resultar más naturales en escenarios que requieren la creación de un especial de un tipo existente (especialización).</span><span class="sxs-lookup"><span data-stu-id="3db1a-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="3db1a-106">Los miembros virtuales funcionan mejor que las devoluciones de llamada y eventos, pero no lleva a cabo un mejor rendimiento que los métodos no virtuales.</span><span class="sxs-lookup"><span data-stu-id="3db1a-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="3db1a-107">La principal desventaja de los miembros virtuales es que solo se puede modificar el comportamiento de un miembro virtual en el momento de la compilación.</span><span class="sxs-lookup"><span data-stu-id="3db1a-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="3db1a-108">El comportamiento de una devolución de llamada puede modificarse en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3db1a-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="3db1a-109">Los miembros virtuales, como las devoluciones de llamada (y quizá algo más que las devoluciones de llamada), son costosos de diseñar, probar y mantener, ya que cualquier llamada a un miembro virtual puede reemplazarse de manera impredecible y puede ejecutar código arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3db1a-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="3db1a-110">Además, mucho más esfuerzo normalmente es necesario definir claramente el contrato de los miembros virtuales, por lo que el costo de diseño y la documentación de ellos es mayor.</span><span class="sxs-lookup"><span data-stu-id="3db1a-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="3db1a-111">**X DO NOT** hacer que los miembros virtuales a menos que tenga una buena razón para hacerlo y tenga en cuenta todos los costes asociados a diseñar, probar y mantener los miembros virtuales.</span><span class="sxs-lookup"><span data-stu-id="3db1a-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="3db1a-112">Los miembros virtuales son menos flexible en cuanto a los cambios que se pueden realizar en ellos sin interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="3db1a-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="3db1a-113">Además, son más lentos que los miembros que no son virtuales, principalmente porque no se alinean las llamadas a los miembros virtuales.</span><span class="sxs-lookup"><span data-stu-id="3db1a-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="3db1a-114">**✓ CONSIDER** limitar la extensibilidad para solo lo que sea absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="3db1a-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="3db1a-115">**✓ DO** preferir accesibilidad protegida accesibilidad pública para los miembros virtuales.</span><span class="sxs-lookup"><span data-stu-id="3db1a-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="3db1a-116">Los miembros públicos deben proporcionar extensibilidad (si es necesario) mediante una llamada a un miembro virtual protegida.</span><span class="sxs-lookup"><span data-stu-id="3db1a-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="3db1a-117">Los miembros públicos de una clase deben proporcionar el conjunto correcto de funcionalidad para los consumidores directos de esa clase.</span><span class="sxs-lookup"><span data-stu-id="3db1a-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="3db1a-118">Los miembros virtuales están diseñados para invalidarse en subclases y accesibilidad protegida es una excelente manera de definir el ámbito de todos los puntos de extensibilidad virtual donde se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="3db1a-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="3db1a-119">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="3db1a-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3db1a-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="3db1a-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db1a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3db1a-121">See also</span></span>

- [<span data-ttu-id="3db1a-122">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3db1a-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="3db1a-123">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="3db1a-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
