---
title: No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: fe95f80d42fc12ab2829db899fe295e32f358db6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059813"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>No se puede llamar a una función friend de un objeto que no sea una instancia de una clase

Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos. Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.  
  
## <a name="see-also"></a>Vea también

- [Friend](../language-reference/modifiers/friend.md)
