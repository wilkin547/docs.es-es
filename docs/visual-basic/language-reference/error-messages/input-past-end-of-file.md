---
title: "Se sobrepasó el final del archivo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
