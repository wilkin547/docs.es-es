---
title: Instrucciones de diseño de excepciones
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: 776e559bb1629245c275cb4463531a8dd4b230ae
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821156"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="1249b-102">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="1249b-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="1249b-103">El control de excepciones tiene muchas ventajas en comparación con los informes de errores basados en valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="1249b-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="1249b-104">Un buen diseño del marco ayuda al desarrollador de la aplicación a obtener las ventajas de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="1249b-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="1249b-105">En esta sección se describen las ventajas de las excepciones y se presentan las directrices para usarlas de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="1249b-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1249b-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1249b-106">In This Section</span></span>  
 [<span data-ttu-id="1249b-107">Inicio de excepción</span><span class="sxs-lookup"><span data-stu-id="1249b-107">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="1249b-108">Usar tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="1249b-108">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="1249b-109">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1249b-109">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="1249b-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1249b-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1249b-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1249b-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1249b-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1249b-112">See also</span></span>

- [<span data-ttu-id="1249b-113">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="1249b-113">Framework Design Guidelines</span></span>](index.md)
