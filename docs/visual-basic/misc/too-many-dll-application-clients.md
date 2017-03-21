---
title: "Demasiados clientes de aplicación DLL | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1abc9ce574de00db42a33cde478ca80be74e61ff
ms.lasthandoff: 03/13/2017

---
# <a name="too-many-dll-application-clients"></a>Demasiados clientes de aplicación DLL
La biblioteca de vínculos dinámicos (DLL) de [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sólo se puede adaptar el acceso mediante un número limitado de aplicaciones host. La aplicación y otras aplicaciones que son [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hosts (algunos de los cuales pueden tener acceso a la aplicación) están intentando tener acceso el [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL al mismo tiempo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Reducir el número de acceso a las aplicaciones [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)
