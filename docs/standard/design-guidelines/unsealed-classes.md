---
title: Clases no selladas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: d7174de7ddf062b829672e04952c1010fcb74058
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616943"
---
# <a name="unsealed-classes"></a><span data-ttu-id="82dfa-102">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="82dfa-102">Unsealed Classes</span></span>
<span data-ttu-id="82dfa-103">Clases selladas no se puede heredar de y evitar la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="82dfa-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="82dfa-104">En cambio, las clases que se pueden heredar se denominan clases no selladas.</span><span class="sxs-lookup"><span data-stu-id="82dfa-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="82dfa-105">**✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="82dfa-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="82dfa-106">Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de conveniencia como constructores personalizados, nuevos métodos o las sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="82dfa-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="82dfa-107">Por ejemplo, `System.Messaging.MessageQueue` está sellado y, por tanto, permite a los usuarios para crear colas personalizadas el valor predeterminado para una ruta de acceso de cola determinada o para agregar métodos personalizados que simplifican la API para escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="82dfa-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="82dfa-108">Las clases están sellados o sin sellar de forma predeterminada en los lenguajes de programación más y esto también es el valor predeterminado recomendado para la mayoría de las clases de marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="82dfa-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="82dfa-109">La extensibilidad ofrecida por los tipos no sellados es mucho más valorados por los usuarios de plataformas y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.</span><span class="sxs-lookup"><span data-stu-id="82dfa-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="82dfa-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="82dfa-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="82dfa-111">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="82dfa-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dfa-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="82dfa-112">See also</span></span>

- [<span data-ttu-id="82dfa-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="82dfa-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="82dfa-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="82dfa-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="82dfa-115">Sellado</span><span class="sxs-lookup"><span data-stu-id="82dfa-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
