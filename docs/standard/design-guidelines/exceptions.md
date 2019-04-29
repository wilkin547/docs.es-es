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
author: KrzysztofCwalina
ms.openlocfilehash: 60c3d25138c224f5eabf44d06b6c9a8373eb5f96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669061"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="6ba60-102">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="6ba60-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="6ba60-103">Control de excepciones presenta muchas ventajas respecto a los informes de errores basado en el valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="6ba60-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="6ba60-104">Diseño de buen marco ayuda a los desarrolladores de aplicaciones aprovechar las ventajas de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="6ba60-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="6ba60-105">En esta sección se describe las ventajas de las excepciones y se muestra instrucciones para usar de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="6ba60-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ba60-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6ba60-106">In This Section</span></span>  
 [<span data-ttu-id="6ba60-107">Inicio de excepción</span><span class="sxs-lookup"><span data-stu-id="6ba60-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="6ba60-108">Uso de tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="6ba60-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="6ba60-109">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="6ba60-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="6ba60-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6ba60-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6ba60-111">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6ba60-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba60-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ba60-112">See also</span></span>

- [<span data-ttu-id="6ba60-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6ba60-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
