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
author: KrzysztofCwalina
ms.openlocfilehash: f25573c0fef29ef54dc04c5287757903429d89d4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615202"
---
# <a name="sealing"></a><span data-ttu-id="ae86c-102">Sellar</span><span class="sxs-lookup"><span data-stu-id="ae86c-102">Sealing</span></span>
<span data-ttu-id="ae86c-103">Una de las características de marcos de trabajo orientado a objetos es que los desarrolladores pueden ampliar y personalizarlos en modos imprevistos por los diseñadores de framework.</span><span class="sxs-lookup"><span data-stu-id="ae86c-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="ae86c-104">Se trata de la eficacia y el peligro de diseño extensible.</span><span class="sxs-lookup"><span data-stu-id="ae86c-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="ae86c-105">Al diseñar su marco, es, por lo tanto, muy importante para diseñar cuidadosamente para la extensibilidad cuando lo desee y para limitar la extensibilidad cuando resulta peligroso.</span><span class="sxs-lookup"><span data-stu-id="ae86c-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="ae86c-106">Un mecanismo eficaz que impide la extensibilidad de sellado.</span><span class="sxs-lookup"><span data-stu-id="ae86c-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="ae86c-107">Puede sellar clases o miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="ae86c-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="ae86c-108">Sellar una clase, impide que los usuarios hereden de la clase.</span><span class="sxs-lookup"><span data-stu-id="ae86c-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="ae86c-109">Sellado de un miembro, impide que los usuarios invalidar a un miembro determinado.</span><span class="sxs-lookup"><span data-stu-id="ae86c-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="ae86c-110">**X DO NOT** sellar clases sin tener una buena razón para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ae86c-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="ae86c-111">Sellar una clase porque no se puede pensar en un escenario de extensibilidad no es una buena razón.</span><span class="sxs-lookup"><span data-stu-id="ae86c-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="ae86c-112">Los usuarios de plataformas como heredar de clases por diversos motivos nonobvious, como agregar miembros de comodidad.</span><span class="sxs-lookup"><span data-stu-id="ae86c-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="ae86c-113">Consulte [clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md) para obtener ejemplos de motivos nonobvious los usuarios desean hereda de un tipo.</span><span class="sxs-lookup"><span data-stu-id="ae86c-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="ae86c-114">Buenas razones para sellar una clase incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae86c-114">Good reasons for sealing a class include the following:</span></span>  
  
- <span data-ttu-id="ae86c-115">La clase es una clase estática.</span><span class="sxs-lookup"><span data-stu-id="ae86c-115">The class is a static class.</span></span> <span data-ttu-id="ae86c-116">Consulte [diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="ae86c-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
- <span data-ttu-id="ae86c-117">La clase almacena los secretos de seguridad en los miembros protegidos heredados.</span><span class="sxs-lookup"><span data-stu-id="ae86c-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
- <span data-ttu-id="ae86c-118">La clase hereda a muchos miembros virtuales y el costo de sellar ellos individualmente superaría con creces las ventajas de salir de la clase no sellada.</span><span class="sxs-lookup"><span data-stu-id="ae86c-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
- <span data-ttu-id="ae86c-119">La clase es un atributo que requiere la búsqueda en tiempo de ejecución muy rápida.</span><span class="sxs-lookup"><span data-stu-id="ae86c-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="ae86c-120">Atributos sealed tienen niveles de rendimiento ligeramente superiores que no sellado que.</span><span class="sxs-lookup"><span data-stu-id="ae86c-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="ae86c-121">consulte [atributos](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ae86c-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="ae86c-122">**X DO NOT** declarar miembros protegidos o virtuales en tipos sealed.</span><span class="sxs-lookup"><span data-stu-id="ae86c-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="ae86c-123">Por definición, tipos sellados no se puede heredar de.</span><span class="sxs-lookup"><span data-stu-id="ae86c-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="ae86c-124">Esto significa que los miembros protegidos en tipos sellados no se puede llamar, y no se puede invalidar los métodos virtuales en tipos sealed.</span><span class="sxs-lookup"><span data-stu-id="ae86c-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="ae86c-125">**✓ CONSIDER** sellar los miembros reemplazados.</span><span class="sxs-lookup"><span data-stu-id="ae86c-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="ae86c-126">Problemas que pueden derivarse de introducción a los miembros virtuales (se describe en [miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)) se aplican a invalidaciones, aunque en un grado ligeramente menor.</span><span class="sxs-lookup"><span data-stu-id="ae86c-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="ae86c-127">Sellar una invalidación intercepta estos problemas a partir de ese punto en la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="ae86c-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="ae86c-128">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="ae86c-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ae86c-129">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ae86c-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae86c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae86c-130">See also</span></span>

- [<span data-ttu-id="ae86c-131">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ae86c-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="ae86c-132">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="ae86c-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="ae86c-133">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="ae86c-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
