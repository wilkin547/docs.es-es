---
title: Clases no selladas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ec66fb3dea74e6f738ec308ce0f88945526a0a77
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="unsealed-classes"></a><span data-ttu-id="18031-102">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="18031-102">Unsealed Classes</span></span>
<span data-ttu-id="18031-103">No se puede heredar clases selladas de e impiden que extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="18031-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="18031-104">En cambio, las clases que se pueden heredar de se denominan clases no selladas.</span><span class="sxs-lookup"><span data-stu-id="18031-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="18031-105">**✓ Considere la posibilidad de** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="18031-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="18031-106">Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de comodidad como constructores personalizados, nuevos métodos o las sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="18031-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="18031-107">Por ejemplo, `System.Messaging.MessageQueue` no está sellado y, por tanto, permite a los usuarios para crear colas personalizadas este comportamiento predeterminado para una ruta de acceso de cola determinado o para agregar métodos personalizados que simplifican la API de escenarios concretos.</span><span class="sxs-lookup"><span data-stu-id="18031-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="18031-108">Las clases están selladas de forma predeterminada en los lenguajes de programación más y también es el valor predeterminado recomendado para la mayoría de las clases en marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="18031-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="18031-109">La extensibilidad ofrecida por los tipos no sellados se valora mucho por los usuarios de framework y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.</span><span class="sxs-lookup"><span data-stu-id="18031-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="18031-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="18031-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="18031-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="18031-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18031-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="18031-112">See Also</span></span>  
 [<span data-ttu-id="18031-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="18031-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="18031-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="18031-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="18031-115">Sellado</span><span class="sxs-lookup"><span data-stu-id="18031-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
