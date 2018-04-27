---
title: Instrucciones de diseño de excepciones
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6dcd29f96ce32f1b2602af5d844339fe33c0ed7b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="991b3-102">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="991b3-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="991b3-103">Control de excepciones tiene muchas ventajas comparado con informe de errores basada en valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="991b3-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="991b3-104">Diseño de buena framework ayuda al desarrollador de aplicaciones tenga en cuenta las ventajas de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="991b3-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="991b3-105">En esta sección se describe las ventajas de las excepciones y se presenta las directrices para usar de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="991b3-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="991b3-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="991b3-106">In This Section</span></span>  
 [<span data-ttu-id="991b3-107">Inicio de excepción</span><span class="sxs-lookup"><span data-stu-id="991b3-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="991b3-108">Uso de tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="991b3-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="991b3-109">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="991b3-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="991b3-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="991b3-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="991b3-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="991b3-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991b3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="991b3-112">See Also</span></span>  
 [<span data-ttu-id="991b3-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="991b3-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
