---
title: No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: d159b9bb3a765a2fefe99fa15dff42e979fda9e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079144"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen

No se pudo realizar una operación cíclica. Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar. Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.  
  
## <a name="see-also"></a>Vea también

- [Tipos de errores](../programming-guide/language-features/error-types.md)
- [Uso de puntos de interrupción en el depurador de Visual Studio](/visualstudio/debugger/using-breakpoints)
