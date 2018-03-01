---
title: "Demasiados clientes de aplicación DLL"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a>Demasiados clientes de aplicación DLL
La biblioteca de vínculos dinámicos (DLL) de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] solo puede admitir el acceso de un número limitado de aplicaciones host. La aplicación y otras aplicaciones que son hosts de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (es posible que su aplicación acceda a algunos de estos) están intentando acceder a la DLL de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] al mismo tiempo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Reduzca el número de aplicaciones abiertas que acceden a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)
