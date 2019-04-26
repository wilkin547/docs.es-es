---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802653"
---
# <a name="file-already-open"></a>Archivo ya abierto
A veces se debe cerrar un archivo antes que otro `FileOpen` o puede producirse otra operación. Entre las causas posibles de este error se incluyen:  
  
-   Modo de salida secuencial `FileOpen` ejecutó la operación para un archivo que ya está abierto  
  
-   La instrucción hace referencia a un archivo abierto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Cierre el archivo antes de ejecutar la instrucción.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
