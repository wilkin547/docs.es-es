---
title: Clases no selladas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571666"
---
# <a name="unsealed-classes"></a><span data-ttu-id="b1d81-102">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="b1d81-102">Unsealed Classes</span></span>
<span data-ttu-id="b1d81-103">No se puede heredar clases selladas de e impiden que extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="b1d81-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="b1d81-104">En cambio, las clases que se pueden heredar de se denominan clases no selladas.</span><span class="sxs-lookup"><span data-stu-id="b1d81-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="b1d81-105">**✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b1d81-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="b1d81-106">Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de comodidad como constructores personalizados, nuevos métodos o las sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="b1d81-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="b1d81-107">Por ejemplo, `System.Messaging.MessageQueue` no está sellado y, por tanto, permite a los usuarios para crear colas personalizadas este comportamiento predeterminado para una ruta de acceso de cola determinado o para agregar métodos personalizados que simplifican la API de escenarios concretos.</span><span class="sxs-lookup"><span data-stu-id="b1d81-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="b1d81-108">Las clases están selladas de forma predeterminada en los lenguajes de programación más y también es el valor predeterminado recomendado para la mayoría de las clases en marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b1d81-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="b1d81-109">La extensibilidad ofrecida por los tipos no sellados se valora mucho por los usuarios de framework y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.</span><span class="sxs-lookup"><span data-stu-id="b1d81-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="b1d81-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="b1d81-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b1d81-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b1d81-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d81-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1d81-112">See Also</span></span>  
 [<span data-ttu-id="b1d81-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b1d81-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="b1d81-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="b1d81-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="b1d81-115">Sellado</span><span class="sxs-lookup"><span data-stu-id="b1d81-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
