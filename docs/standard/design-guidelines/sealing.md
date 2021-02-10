---
description: 'Más información acerca de: Sellar'
title: Sellar
ms.date: 10/22/2008
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: 94673f793aa7373e1076e13cbda900fba83786f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731726"
---
# <a name="sealing"></a><span data-ttu-id="d413d-103">Sellar</span><span class="sxs-lookup"><span data-stu-id="d413d-103">Sealing</span></span>

<span data-ttu-id="d413d-104">Una de las características de los marcos orientados a objetos es que los desarrolladores pueden ampliarlos y personalizarlos de formas imprevistas para los diseñadores de marcos.</span><span class="sxs-lookup"><span data-stu-id="d413d-104">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="d413d-105">Esta es la eficacia y el peligro del diseño extensible.</span><span class="sxs-lookup"><span data-stu-id="d413d-105">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="d413d-106">Al diseñar el marco, es, por lo tanto, muy importante diseñar cuidadosamente para la extensibilidad cuando se desee y limitar esta cuando haya peligro.</span><span class="sxs-lookup"><span data-stu-id="d413d-106">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="d413d-107">Un mecanismo eficaz que evita la extensibilidad es el sellado.</span><span class="sxs-lookup"><span data-stu-id="d413d-107">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="d413d-108">Puede sellar los miembros individuales o de clase.</span><span class="sxs-lookup"><span data-stu-id="d413d-108">You can seal either the class or individual members.</span></span> <span data-ttu-id="d413d-109">Sellar una clase impide que los usuarios hereden de la clase.</span><span class="sxs-lookup"><span data-stu-id="d413d-109">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="d413d-110">Sellar un miembro impide que los usuarios invaliden un miembro determinado.</span><span class="sxs-lookup"><span data-stu-id="d413d-110">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="d413d-111">❌ NO selle clases sin tener una buena razón para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d413d-111">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="d413d-112">Sellar una clase porque no puede pensar en un escenario de extensibilidad no es una buena razón.</span><span class="sxs-lookup"><span data-stu-id="d413d-112">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="d413d-113">A los usuarios del marco les gusta heredar de clases por diversas razones no evidentes, como la incorporación de miembros de conveniencia.</span><span class="sxs-lookup"><span data-stu-id="d413d-113">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="d413d-114">Consulte [Clases no selladas](unsealed-classes.md) por ver ejemplos de razones no evidentes que los usuarios desean heredar de un tipo.</span><span class="sxs-lookup"><span data-stu-id="d413d-114">See [Unsealed Classes](unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="d413d-115">Entre las razones buenas para sellar una clase se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d413d-115">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="d413d-116">La clase es una clase estática.</span><span class="sxs-lookup"><span data-stu-id="d413d-116">The class is a static class.</span></span> <span data-ttu-id="d413d-117">Consulte [Diseño de clases estáticas](static-class.md).</span><span class="sxs-lookup"><span data-stu-id="d413d-117">See [Static Class Design](static-class.md).</span></span>

- <span data-ttu-id="d413d-118">La clase almacena secretos que afectan a la seguridad en miembros protegidos heredados.</span><span class="sxs-lookup"><span data-stu-id="d413d-118">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="d413d-119">La clase hereda muchos miembros virtuales y el costo de sellarlos individualmente superaría las ventajas de dejar la clase sin sellar.</span><span class="sxs-lookup"><span data-stu-id="d413d-119">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="d413d-120">La clase es un atributo que requiere una búsqueda de tiempo de ejecución muy rápida.</span><span class="sxs-lookup"><span data-stu-id="d413d-120">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="d413d-121">Los atributos sellados tienen niveles de rendimiento ligeramente mayores que los no sellados.</span><span class="sxs-lookup"><span data-stu-id="d413d-121">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="d413d-122">Consulte [Atributos](attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d413d-122">See [Attributes](attributes.md).</span></span>

 <span data-ttu-id="d413d-123">❌ NO declare miembros protegidos ni virtuales en tipos sellados.</span><span class="sxs-lookup"><span data-stu-id="d413d-123">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="d413d-124">Por definición, los tipos sellados no se pueden heredar de ahí.</span><span class="sxs-lookup"><span data-stu-id="d413d-124">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="d413d-125">Esto significa que no se puede llamar a los miembros protegidos en tipos sellados y que tampoco se pueden invalidar los métodos virtuales en tipos sellados.</span><span class="sxs-lookup"><span data-stu-id="d413d-125">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="d413d-126">✔️ CONSIDERE la posibilidad de sellar los miembros que invalide.</span><span class="sxs-lookup"><span data-stu-id="d413d-126">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="d413d-127">Los problemas que pueden surgir de la presentación de miembros virtuales (como se indica en [Miembros virtuales](virtual-members.md)) se aplican también a las invalidaciones, aunque en un grado ligeramente menor.</span><span class="sxs-lookup"><span data-stu-id="d413d-127">Problems that can result from introducing virtual members (discussed in [Virtual Members](virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="d413d-128">Sellar una invalidación le protege de estos problemas a partir de ese punto en la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="d413d-128">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="d413d-129">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="d413d-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d413d-130">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="d413d-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d413d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d413d-131">See also</span></span>

- [<span data-ttu-id="d413d-132">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d413d-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d413d-133">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="d413d-133">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="d413d-134">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="d413d-134">Unsealed Classes</span></span>](unsealed-classes.md)
