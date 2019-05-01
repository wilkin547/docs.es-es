---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970123"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
No se pudo realizar una operación cíclica. Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar. Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.  
  
## <a name="see-also"></a>Vea también

- [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)
- [Utilizar puntos de interrupción en el depurador de Visual Studio](/visualstudio/debugger/using-breakpoints)
