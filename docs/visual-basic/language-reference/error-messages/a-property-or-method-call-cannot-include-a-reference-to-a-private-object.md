---
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 1f36526eab1bc0964bf89398b6e0f3e74d09fdc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
Entre las causas posibles de este error se incluyen:  
  
-   Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.  
  
-   Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.  
  
-   Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.  
  
-   Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Quite la referencia.  
  
## <a name="see-also"></a>Vea también  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)
