---
title: "No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 429d679157d25655ca73afef14ecd642f7cac37f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen
No se pudo realizar una operación cíclica. Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar. Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Fundamentos de la depuración: puntos de interrupción](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
