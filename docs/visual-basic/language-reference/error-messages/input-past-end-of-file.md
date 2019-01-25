---
title: Se sobrepasó el final del archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 29a9b5ce3c3f8e6a02b52beda1338fd699143570
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491342"
---
# <a name="input-past-end-of-file"></a>Se sobrepasó el final del archivo
Ya sea un `Input` instrucción está leyendo desde un archivo que está vacío o uno en el que todos los datos se usa o ha usado el `EOF` función con un archivo abierto para acceso binario.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Use la `EOF` función inmediatamente antes de la `Input` instrucción para detectar el final del archivo.  
  
2.  Si el archivo está abierto para acceso binario, utilice `Seek` y `Loc`.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
