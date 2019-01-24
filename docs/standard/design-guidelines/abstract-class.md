---
title: Diseño de clases abstractas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550420"
---
# <a name="abstract-class-design"></a><span data-ttu-id="371df-102">Diseño de clases abstractas</span><span class="sxs-lookup"><span data-stu-id="371df-102">Abstract Class Design</span></span>
<span data-ttu-id="371df-103">**X DO NOT** definir constructores internos públicos o protegidos en tipos abstractos.</span><span class="sxs-lookup"><span data-stu-id="371df-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="371df-104">Los constructores deberían ser públicos solo si los usuarios tendrán que crear instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="371df-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="371df-105">Dado que no se puede crear instancias de un tipo abstracto, un tipo abstracto con un constructor público está incorrectamente diseñado y puede inducir a error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="371df-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="371df-106">**✓ DO** definir un constructor interno o protegidos en las clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="371df-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="371df-107">Un constructor protegido es más común y simplemente permite que la clase base para realizar su propia inicialización cuando se crean subtipos.</span><span class="sxs-lookup"><span data-stu-id="371df-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="371df-108">Un constructor interno puede utilizarse para limitar las implementaciones concretas de la clase abstracta para el ensamblado que define la clase.</span><span class="sxs-lookup"><span data-stu-id="371df-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="371df-109">**✓ DO** proporcionar al menos un tipo concreto que herede de cada clase abstracta que realiza el envío.</span><span class="sxs-lookup"><span data-stu-id="371df-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="371df-110">Si hace esto ayuda a validar el diseño de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="371df-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="371df-111">Por ejemplo, <xref:System.IO.FileStream?displayProperty=nameWithType> es una implementación de la <xref:System.IO.Stream?displayProperty=nameWithType> clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="371df-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="371df-112">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="371df-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="371df-113">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="371df-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="371df-114">See also</span></span>

- [<span data-ttu-id="371df-115">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="371df-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="371df-116">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="371df-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
