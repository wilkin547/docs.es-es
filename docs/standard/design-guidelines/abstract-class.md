---
description: 'Más información acerca de: Diseño de clases abstractas'
title: Diseño de clases abstractas
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 5b1cd833bf43e5bf5731176243809393187e84d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642466"
---
# <a name="abstract-class-design"></a><span data-ttu-id="bdeef-103">Diseño de clases abstractas</span><span class="sxs-lookup"><span data-stu-id="bdeef-103">Abstract Class Design</span></span>

<span data-ttu-id="bdeef-104">❌ NO defina constructores internos públicos o protegidos en tipos abstractos.</span><span class="sxs-lookup"><span data-stu-id="bdeef-104">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="bdeef-105">Los constructores solo deben ser públicos si los usuarios deben crear instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="bdeef-105">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="bdeef-106">Puesto que no se pueden crear instancias de un tipo abstracto, no es correcto diseñar un tipo abstracto con un constructor público y confundir a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bdeef-106">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="bdeef-107">✔️ Defina un constructor protegido o interno en clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="bdeef-107">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="bdeef-108">Un constructor protegido es más común y simplemente permite que la clase base realice su propia inicialización cuando se creen subtipos.</span><span class="sxs-lookup"><span data-stu-id="bdeef-108">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="bdeef-109">Se puede usar un constructor interno para limitar las implementaciones concretas de la clase abstracta al ensamblado que define la clase.</span><span class="sxs-lookup"><span data-stu-id="bdeef-109">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="bdeef-110">✔️ Proporcione al menos un tipo concreto que hereda de cada clase abstracta que se envíe.</span><span class="sxs-lookup"><span data-stu-id="bdeef-110">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="bdeef-111">Esto ayuda a validar el diseño de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="bdeef-111">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="bdeef-112">Por ejemplo, <xref:System.IO.FileStream?displayProperty=nameWithType> es una implementación de la clase abstracta <xref:System.IO.Stream?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bdeef-112">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="bdeef-113">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="bdeef-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="bdeef-114">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="bdeef-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="bdeef-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdeef-115">See also</span></span>

- [<span data-ttu-id="bdeef-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="bdeef-116">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="bdeef-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bdeef-117">Framework Design Guidelines</span></span>](index.md)
