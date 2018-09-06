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
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891382"
---
# <a name="unsealed-classes"></a><span data-ttu-id="7be8f-102">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="7be8f-102">Unsealed Classes</span></span>
<span data-ttu-id="7be8f-103">Clases selladas no se puede heredar de y evitar la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="7be8f-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="7be8f-104">En cambio, las clases que se pueden heredar se denominan clases no selladas.</span><span class="sxs-lookup"><span data-stu-id="7be8f-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="7be8f-105">**✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7be8f-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="7be8f-106">Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de conveniencia como constructores personalizados, nuevos métodos o las sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="7be8f-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="7be8f-107">Por ejemplo, `System.Messaging.MessageQueue` está sellado y, por tanto, permite a los usuarios para crear colas personalizadas el valor predeterminado para una ruta de acceso de cola determinada o para agregar métodos personalizados que simplifican la API para escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="7be8f-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="7be8f-108">Las clases están sellados o sin sellar de forma predeterminada en los lenguajes de programación más y esto también es el valor predeterminado recomendado para la mayoría de las clases de marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7be8f-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="7be8f-109">La extensibilidad ofrecida por los tipos no sellados es mucho más valorados por los usuarios de plataformas y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.</span><span class="sxs-lookup"><span data-stu-id="7be8f-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="7be8f-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="7be8f-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7be8f-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="7be8f-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be8f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7be8f-112">See also</span></span>

- [<span data-ttu-id="7be8f-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7be8f-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="7be8f-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="7be8f-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="7be8f-115">Sellado</span><span class="sxs-lookup"><span data-stu-id="7be8f-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
