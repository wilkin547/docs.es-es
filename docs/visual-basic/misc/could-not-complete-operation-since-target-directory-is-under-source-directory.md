---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: b821034731514362a3725c390e02542b536f0a59
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890809"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
No se pudo realizar una operación cíclica. Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar. Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Fundamentos de la depuración: puntos de interrupción](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
