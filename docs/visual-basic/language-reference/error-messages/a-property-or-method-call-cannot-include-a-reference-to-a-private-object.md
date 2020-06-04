---
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 36c71cdb345d0fdc0da2b58865a1f11956bcb944
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409977"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno

Entre las causas posibles de este error se incluyen:  
  
- Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.  
  
- Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.  
  
- Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.  
  
- Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Quite la referencia.  
  
## <a name="see-also"></a>Consulte también

- [Privado](../modifiers/private.md)
