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
ms.openlocfilehash: 99b27615ef16aa69e18d82cb97f4751dc92d2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570608"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="c195a-102">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="c195a-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="c195a-103">Control de excepciones tiene muchas ventajas comparado con informe de errores basada en valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="c195a-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="c195a-104">Diseño de buena framework ayuda al desarrollador de aplicaciones tenga en cuenta las ventajas de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="c195a-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="c195a-105">En esta sección se describe las ventajas de las excepciones y se presenta las directrices para usar de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="c195a-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c195a-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c195a-106">In This Section</span></span>  
 [<span data-ttu-id="c195a-107">Inicio de excepción</span><span class="sxs-lookup"><span data-stu-id="c195a-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="c195a-108">Uso de tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="c195a-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="c195a-109">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="c195a-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="c195a-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="c195a-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c195a-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c195a-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c195a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c195a-112">See Also</span></span>  
 [<span data-ttu-id="c195a-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c195a-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
