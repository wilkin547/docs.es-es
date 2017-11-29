---
title: No se pudo obtener un flujo para el registro
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd3051b2331502c9f4f3430bbf88731b307d1b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>No se pudo obtener un flujo para el registro
No se pudo obtener un flujo para el registro. Los nombres de archivo potenciales basados en \<nombre > ya están en uso.  
  
 El <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> clase no pudo crear un nuevo archivo de registro porque todos los posibles nombres de archivo de registro se basan en \<nombre > ya están en uso.  
  
 Si dispone de demasiados archivos de registro, podría ser un indicador de un problema de arquitectura con la aplicación. Consulte la documentación sobre la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> para más información.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> en <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> para incluir una marca de fecha en el nombre del archivo de registro.  
  
2.  Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [My.Application.Log (objeto)](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [My.Log (objeto)](../../visual-basic/language-reference/objects/my-log-object.md)
