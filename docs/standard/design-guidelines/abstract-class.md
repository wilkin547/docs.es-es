---
title: "Diseño de clases abstractas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 739f86acd534549bc997dc7a939cf43a0c6fc3cb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="abstract-class-design"></a><span data-ttu-id="6fb5c-102">Diseño de clases abstractas</span><span class="sxs-lookup"><span data-stu-id="6fb5c-102">Abstract Class Design</span></span>
<span data-ttu-id="6fb5c-103">**X DO NOT** definir constructores internos públicos o protegidos en tipos abstractos.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="6fb5c-104">Los constructores deberían ser públicos sólo si los usuarios deberán crear instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="6fb5c-105">Dado que no se puede crear instancias de un tipo abstracto, un tipo abstracto con un constructor público es incorrectamente se ha diseñado y puede inducir a error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="6fb5c-106">**✓ HACER** definir un constructor interno o protegidos en las clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="6fb5c-107">Un constructor protegido es más común y simplemente permite que la clase base para realizar su propia inicialización cuando se crean subtipos.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="6fb5c-108">Un constructor interno puede utilizarse para limitar las implementaciones concretas de la clase abstracta para el ensamblado que define la clase.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="6fb5c-109">**✓ HACER** proporcionar al menos un tipo concreto que herede de cada clase abstracta que realiza el envío.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="6fb5c-110">Haciendo esto ayuda a validar el diseño de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="6fb5c-111">Por ejemplo, <xref:System.IO.FileStream?displayProperty=nameWithType> es una implementación de la <xref:System.IO.Stream?displayProperty=nameWithType> clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="6fb5c-112">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6fb5c-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6fb5c-113">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6fb5c-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb5c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fb5c-114">See Also</span></span>  
 [<span data-ttu-id="6fb5c-115">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="6fb5c-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="6fb5c-116">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6fb5c-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
