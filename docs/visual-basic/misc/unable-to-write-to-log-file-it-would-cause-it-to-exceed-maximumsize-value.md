---
title: "No se puede escribir en el archivo de registro porque se superaría el valor de MaximumSize"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b4d284f9e1a79e409a41aed57ec880fc371b8332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>No se puede escribir en el archivo de registro porque se superaría el valor de MaximumSize
La clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> no pudo escribir en el archivo de registro porque:  
  
-   El tamaño del archivo de registro (en bytes) es mayor que el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>   
  
     y  
  
-   El valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> es <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.  
  
2.  Cambie el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> para permitir que los registros tengan mayor tamaño.  
  
3.  Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> en <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> para descartar los mensajes sin advertir si el registro es demasiado grande.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [My.Application.Log (objeto)](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [My.Log (objeto)](../../visual-basic/language-reference/objects/my-log-object.md)
