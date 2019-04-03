---
title: Se sobrepasó el final del archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 63b099144b9da601a7b52a738f5a3173097ae257
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813163"
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
