---
title: Archivo ya abierto
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a>Archivo ya abierto
A veces se debe cerrar un archivo antes que otro `FileOpen` o se puede realizar otra operación. Entre las causas posibles de este error se incluyen:  
  
-   Modo de salida secuencial `FileOpen` ha ejecutado una operación para un archivo que ya está abierto  
  
-   Una instrucción hace referencia a un archivo abierto.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Cierre el archivo antes de ejecutar la instrucción.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
