---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823511"
---
# <a name="file-already-open"></a>Archivo ya abierto
A veces se debe cerrar un archivo antes que otro `FileOpen` o puede producirse otra operación. Entre las causas posibles de este error se incluyen:  
  
-   Modo de salida secuencial `FileOpen` ejecutó la operación para un archivo que ya está abierto  
  
-   La instrucción hace referencia a un archivo abierto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Cierre el archivo antes de ejecutar la instrucción.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
