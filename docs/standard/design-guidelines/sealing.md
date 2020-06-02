---
title: Sellar
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: a54c68efb4ac114fe0e5a5712eca877bef35c103
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290115"
---
# <a name="sealing"></a><span data-ttu-id="932f8-102">Sellar</span><span class="sxs-lookup"><span data-stu-id="932f8-102">Sealing</span></span>
<span data-ttu-id="932f8-103">Una de las características de los marcos de trabajo orientados a objetos es que los desarrolladores pueden ampliarlas y personalizarlas de maneras inesperadas por los diseñadores de Marcos.</span><span class="sxs-lookup"><span data-stu-id="932f8-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="932f8-104">Esta es la eficacia y el peligro del diseño extensible.</span><span class="sxs-lookup"><span data-stu-id="932f8-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="932f8-105">Al diseñar el marco de trabajo, es, por lo tanto, muy importante diseñar cuidadosamente la extensibilidad para que se desee y limitar la extensibilidad cuando sea peligrosa.</span><span class="sxs-lookup"><span data-stu-id="932f8-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="932f8-106">Un mecanismo eficaz que evita la extensibilidad es el sellado.</span><span class="sxs-lookup"><span data-stu-id="932f8-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="932f8-107">Puede sellar la clase o los miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="932f8-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="932f8-108">Sellar una clase impide que los usuarios hereden de la clase.</span><span class="sxs-lookup"><span data-stu-id="932f8-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="932f8-109">El sellado de un miembro impide que los usuarios invaliden un miembro determinado.</span><span class="sxs-lookup"><span data-stu-id="932f8-109">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="932f8-110">❌No selle clases sin tener una buena razón para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="932f8-110">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="932f8-111">Sellar una clase porque no se puede pensar en un escenario de extensibilidad no es una buena razón.</span><span class="sxs-lookup"><span data-stu-id="932f8-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="932f8-112">Los usuarios del marco de trabajo como para heredar de clases por diversos motivos no obvios, como agregar miembros de conveniencia.</span><span class="sxs-lookup"><span data-stu-id="932f8-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="932f8-113">Consulte [clases no selladas](unsealed-classes.md) para obtener ejemplos de razones no obvias que los usuarios desean heredar de un tipo.</span><span class="sxs-lookup"><span data-stu-id="932f8-113">See [Unsealed Classes](unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="932f8-114">Los motivos buenos para sellar una clase son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="932f8-114">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="932f8-115">La clase es una clase estática.</span><span class="sxs-lookup"><span data-stu-id="932f8-115">The class is a static class.</span></span> <span data-ttu-id="932f8-116">Vea [diseño de clases estáticas](static-class.md).</span><span class="sxs-lookup"><span data-stu-id="932f8-116">See [Static Class Design](static-class.md).</span></span>

- <span data-ttu-id="932f8-117">La clase almacena secretos confidenciales de seguridad en miembros protegidos heredados.</span><span class="sxs-lookup"><span data-stu-id="932f8-117">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="932f8-118">La clase hereda muchos miembros virtuales y el costo de sellarlas individualmente superaría las ventajas de mantener la clase sin sellar.</span><span class="sxs-lookup"><span data-stu-id="932f8-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="932f8-119">La clase es un atributo que requiere una búsqueda muy rápida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="932f8-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="932f8-120">Los atributos sellados tienen niveles de rendimiento ligeramente mayores que los no sellados.</span><span class="sxs-lookup"><span data-stu-id="932f8-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="932f8-121">Vea [atributos](attributes.md).</span><span class="sxs-lookup"><span data-stu-id="932f8-121">See [Attributes](attributes.md).</span></span>

 <span data-ttu-id="932f8-122">❌NO declare miembros protegidos o virtuales en tipos sellados.</span><span class="sxs-lookup"><span data-stu-id="932f8-122">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="932f8-123">Por definición, los tipos sellados no se pueden heredar de.</span><span class="sxs-lookup"><span data-stu-id="932f8-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="932f8-124">Esto significa que no se puede llamar a los miembros protegidos en tipos sellados y no se pueden invalidar los métodos virtuales en tipos sellados.</span><span class="sxs-lookup"><span data-stu-id="932f8-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="932f8-125">✔️ considere la posibilidad de sellar los miembros que invalide.</span><span class="sxs-lookup"><span data-stu-id="932f8-125">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="932f8-126">Los problemas que pueden derivarse de la introducción de miembros virtuales (descritos en [miembros virtuales](virtual-members.md)) también se aplican a las invalidaciones, aunque a un grado ligeramente inferior.</span><span class="sxs-lookup"><span data-stu-id="932f8-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="932f8-127">Sellar una invalidación le protege de estos problemas a partir de ese punto en la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="932f8-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="932f8-128">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="932f8-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="932f8-129">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="932f8-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="932f8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="932f8-130">See also</span></span>

- [<span data-ttu-id="932f8-131">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="932f8-131">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="932f8-132">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="932f8-132">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="932f8-133">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="932f8-133">Unsealed Classes</span></span>](unsealed-classes.md)
