---
title: Miembros virtuales
ms.date: 10/22/2008
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 7727ea7fcfdbbecf2e53ddd7a44b4cf907211f80
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734353"
---
# <a name="virtual-members"></a><span data-ttu-id="401e4-102">Miembros virtuales</span><span class="sxs-lookup"><span data-stu-id="401e4-102">Virtual Members</span></span>

<span data-ttu-id="401e4-103">Los miembros virtuales se pueden invalidar, lo que cambia el comportamiento de la subclase.</span><span class="sxs-lookup"><span data-stu-id="401e4-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="401e4-104">Son bastante similares a las devoluciones de llamada en términos de extensibilidad que proporcionan, pero son mejores en cuanto al rendimiento de la ejecución y el consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="401e4-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="401e4-105">Además, los miembros virtuales se sienten más naturales en escenarios que requieren la creación de una clase especial de un tipo existente (especialización).</span><span class="sxs-lookup"><span data-stu-id="401e4-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>

 <span data-ttu-id="401e4-106">Los miembros virtuales funcionan mejor que las devoluciones de llamada y los eventos, pero no funcionan mejor que los métodos no virtuales.</span><span class="sxs-lookup"><span data-stu-id="401e4-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>

 <span data-ttu-id="401e4-107">El principal inconveniente de los miembros virtuales es que el comportamiento de un miembro virtual solo se puede modificar en el momento de la compilación.</span><span class="sxs-lookup"><span data-stu-id="401e4-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="401e4-108">El comportamiento de una devolución de llamada se puede modificar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="401e4-108">The behavior of a callback can be modified at runtime.</span></span>

 <span data-ttu-id="401e4-109">Los miembros virtuales, como las devoluciones de llamada (y quizás más que las devoluciones de llamada), son caros de diseñar, probar y mantener, ya que cualquier llamada a un miembro virtual se puede invalidar de maneras imprevisibles y puede ejecutar código arbitrario.</span><span class="sxs-lookup"><span data-stu-id="401e4-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="401e4-110">Además, normalmente se requiere mucho más esfuerzo para definir claramente el contrato de los miembros virtuales, por lo que el costo de diseñar y documentarlos es mayor.</span><span class="sxs-lookup"><span data-stu-id="401e4-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>

 <span data-ttu-id="401e4-111">❌ NO haga que los miembros sean virtuales a menos que tenga una buena razón para hacerlo y conozca todos los costos relacionados con el diseño, la prueba y el mantenimiento de los miembros virtuales.</span><span class="sxs-lookup"><span data-stu-id="401e4-111">❌ DO NOT make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>

 <span data-ttu-id="401e4-112">Los miembros virtuales son menos permisivo en lo que se refiere a los cambios que se pueden realizar en ellos sin interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="401e4-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="401e4-113">Además, son más lentos que los miembros no virtuales, principalmente porque las llamadas a miembros virtuales no se insertan.</span><span class="sxs-lookup"><span data-stu-id="401e4-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>

 <span data-ttu-id="401e4-114">✔️ considere la posibilidad de limitar la extensibilidad solo a lo que es absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="401e4-114">✔️ CONSIDER limiting extensibility to only what is absolutely necessary.</span></span>

 <span data-ttu-id="401e4-115">✔️ preferir accesibilidad protegida a través de la accesibilidad pública para los miembros virtuales.</span><span class="sxs-lookup"><span data-stu-id="401e4-115">✔️ DO prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="401e4-116">Los miembros públicos deben proporcionar extensibilidad (si es necesario) llamando a un miembro virtual protegido.</span><span class="sxs-lookup"><span data-stu-id="401e4-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>

 <span data-ttu-id="401e4-117">Los miembros públicos de una clase deben proporcionar el conjunto adecuado de funcionalidad para los consumidores directos de esa clase.</span><span class="sxs-lookup"><span data-stu-id="401e4-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="401e4-118">Los miembros virtuales están diseñados para invalidarse en las subclases y la accesibilidad protegida es una excelente manera de definir el ámbito de todos los puntos de extensibilidad virtual en donde se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="401e4-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>

 <span data-ttu-id="401e4-119">*Partes &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="401e4-119">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="401e4-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="401e4-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="401e4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="401e4-121">See also</span></span>

- [<span data-ttu-id="401e4-122">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="401e4-122">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="401e4-123">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="401e4-123">Designing for Extensibility</span></span>](designing-for-extensibility.md)
