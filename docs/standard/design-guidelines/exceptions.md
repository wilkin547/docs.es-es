---
title: Instrucciones de diseño de excepciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51cc5296a7b3f6d75b5e56d6bbc74330fa147848
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703744"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="3185e-102">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="3185e-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="3185e-103">Control de excepciones presenta muchas ventajas respecto a los informes de errores basado en el valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="3185e-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="3185e-104">Diseño de buen marco ayuda a los desarrolladores de aplicaciones aprovechar las ventajas de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="3185e-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="3185e-105">En esta sección se describe las ventajas de las excepciones y se muestra instrucciones para usar de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="3185e-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3185e-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3185e-106">In This Section</span></span>  
 [<span data-ttu-id="3185e-107">Inicio de excepción</span><span class="sxs-lookup"><span data-stu-id="3185e-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="3185e-108">Uso de tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="3185e-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="3185e-109">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="3185e-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="3185e-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="3185e-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3185e-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="3185e-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3185e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3185e-112">See also</span></span>

- [<span data-ttu-id="3185e-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3185e-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
