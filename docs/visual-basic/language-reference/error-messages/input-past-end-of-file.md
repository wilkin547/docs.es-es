---
title: Se sobrepasó el final del archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586746"
---
# <a name="input-past-end-of-file"></a>Se sobrepasó el final del archivo
Ya sea un `Input` instrucción está leyendo de un archivo que está vacío o uno en el que se usan todos los datos o usa el `EOF` función con un archivo abierto para acceso binario.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Use la `EOF` funcionen inmediatamente antes de la `Input` instrucción para detectar el final del archivo.  
  
2.  Si el archivo está abierto para acceso binario, utilice `Seek` y `Loc`.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
