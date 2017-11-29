---
title: "Demasiados clientes de aplicación DLL"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="b8254-102">Demasiados clientes de aplicación DLL</span><span class="sxs-lookup"><span data-stu-id="b8254-102">Too many DLL application clients</span></span>
<span data-ttu-id="b8254-103">La biblioteca de vínculos dinámicos (DLL) de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] solo puede admitir el acceso de un número limitado de aplicaciones host.</span><span class="sxs-lookup"><span data-stu-id="b8254-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="b8254-104">La aplicación y otras aplicaciones que son hosts de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (es posible que su aplicación acceda a algunos de estos) están intentando acceder a la DLL de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b8254-104">Your application and other applications that are [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b8254-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b8254-105">To correct this error</span></span>  
  
-   <span data-ttu-id="b8254-106">Reduzca el número de aplicaciones abiertas que acceden a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8254-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8254-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8254-107">See Also</span></span>  
 [<span data-ttu-id="b8254-108">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="b8254-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
