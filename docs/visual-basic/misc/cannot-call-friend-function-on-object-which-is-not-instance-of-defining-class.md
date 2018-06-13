---
title: No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: a655207110d512805490b693e413b1d22b0367ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33634939"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos. Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.  
  
## <a name="see-also"></a>Vea también  
 [Friend](../../visual-basic/language-reference/modifiers/friend.md)
