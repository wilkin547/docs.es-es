---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 39373cd368282f3b109b450189561366b9e74484
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200577"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
No se pudo realizar una operación cíclica. Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar. Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.  
  
## <a name="see-also"></a>Vea también
- [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)
- [Utilizar puntos de interrupción en el depurador de Visual Studio](/visualstudio/debugger/using-breakpoints)
