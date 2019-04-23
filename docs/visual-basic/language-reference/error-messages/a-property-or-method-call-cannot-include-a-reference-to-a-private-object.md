---
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 04124ca044ad8dbff58f85230d7e10ea336d41e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341483"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
Entre las causas posibles de este error se incluyen:  
  
-   Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.  
  
-   Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.  
  
-   Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.  
  
-   Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Quite la referencia.  
  
## <a name="see-also"></a>Vea también

- [Private](../../../visual-basic/language-reference/modifiers/private.md)
