---
title: Clases no selladas
ms.date: 10/22/2008
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: b2e14b435aa567f231230da34307014210d46ccb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828522"
---
# <a name="unsealed-classes"></a><span data-ttu-id="291eb-102">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="291eb-102">Unsealed Classes</span></span>
<span data-ttu-id="291eb-103">Las clases selladas no se pueden heredar de e impiden la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="291eb-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="291eb-104">Por el contrario, las clases que se pueden heredar de se denominan clases no selladas.</span><span class="sxs-lookup"><span data-stu-id="291eb-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>

 <span data-ttu-id="291eb-105">✔️ considere la posibilidad de usar clases no selladas sin miembros virtuales o protegidos agregados como una excelente manera de proporcionar extensibilidad económica pero mucho más apreciada a un marco.</span><span class="sxs-lookup"><span data-stu-id="291eb-105">✔️ CONSIDER using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>

 <span data-ttu-id="291eb-106">A menudo, los desarrolladores quieren heredar de clases no selladas para agregar a miembros prácticos como constructores personalizados, métodos nuevos o sobrecargas de métodos.</span><span class="sxs-lookup"><span data-stu-id="291eb-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="291eb-107">Por ejemplo,  `System.Messaging.MessageQueue` no está sellado y, por lo tanto, permite a los usuarios crear colas personalizadas que tienen como valor predeterminado una ruta de acceso de cola determinada o agregar métodos personalizados que simplifican la API en escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="291eb-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>

 <span data-ttu-id="291eb-108">De forma predeterminada, las clases no están selladas en la mayoría de los lenguajes de programación, y también es el valor predeterminado recomendado para la mayoría de las clases de Marcos.</span><span class="sxs-lookup"><span data-stu-id="291eb-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="291eb-109">La extensibilidad que ofrecen los tipos no sellados es muy apreciada por los usuarios del marco de trabajo y es bastante barata de proporcionar debido a costos de pruebas relativamente bajos asociados a tipos no sellados.</span><span class="sxs-lookup"><span data-stu-id="291eb-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>

 <span data-ttu-id="291eb-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="291eb-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="291eb-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="291eb-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="291eb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="291eb-112">See also</span></span>

- [<span data-ttu-id="291eb-113">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="291eb-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="291eb-114">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="291eb-114">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="291eb-115">Sellar</span><span class="sxs-lookup"><span data-stu-id="291eb-115">Sealing</span></span>](sealing.md)
