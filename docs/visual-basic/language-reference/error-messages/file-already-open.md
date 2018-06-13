---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 75a08b411a4afd7ea8e11953f1d465b082faa712
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586675"
---
# <a name="file-already-open"></a>Archivo ya abierto
A veces se debe cerrar un archivo antes que otro `FileOpen` o se puede realizar otra operación. Entre las causas posibles de este error se incluyen:  
  
-   Modo de salida secuencial `FileOpen` ha ejecutado una operación para un archivo que ya está abierto  
  
-   Una instrucción hace referencia a un archivo abierto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Cierre el archivo antes de ejecutar la instrucción.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
