---
title: Instrucciones de diseño de excepciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: b64b6052aeb99c6e878c1a9aac50e67bca7f8d2a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709379"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="cc63d-102">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="cc63d-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="cc63d-103">El control de excepciones tiene muchas ventajas en comparación con los informes de errores basados en valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="cc63d-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="cc63d-104">Un buen diseño del marco ayuda al desarrollador de la aplicación a obtener las ventajas de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="cc63d-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="cc63d-105">En esta sección se describen las ventajas de las excepciones y se presentan las directrices para usarlas de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="cc63d-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc63d-106">Esta sección</span><span class="sxs-lookup"><span data-stu-id="cc63d-106">In This Section</span></span>  
 [<span data-ttu-id="cc63d-107">Inicio de excepción</span><span class="sxs-lookup"><span data-stu-id="cc63d-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="cc63d-108">Uso de tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="cc63d-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="cc63d-109">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="cc63d-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="cc63d-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="cc63d-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cc63d-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="cc63d-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc63d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc63d-112">See also</span></span>

- [<span data-ttu-id="cc63d-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc63d-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
