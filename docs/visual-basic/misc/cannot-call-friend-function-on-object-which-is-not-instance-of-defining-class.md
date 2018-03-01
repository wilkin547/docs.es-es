---
title: "No se puede llamar a una función friend de un objeto que no sea una instancia de una clase"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f1ac1ea14efb0cdf0d8ca03257e4da33d35e368
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos. Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.  
  
## <a name="see-also"></a>Vea también  
 [Friend](../../visual-basic/language-reference/modifiers/friend.md)
