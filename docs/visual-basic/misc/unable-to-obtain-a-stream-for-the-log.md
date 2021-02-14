---
description: 'Más información acerca de: no se puede obtener un flujo para el registro'
title: No se pudo obtener un flujo para el registro
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 6eda12eb4dc2b3cf303e543a66e1f2f7d739eb6b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455280"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>No se pudo obtener un flujo para el registro

No se pudo obtener un flujo para el registro. Los nombres de archivo potenciales basados en \<name> ya están en uso.  
  
 La <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> clase no pudo crear un nuevo archivo de registro porque todos los nombres de archivo de registro posibles basados en \<name> ya están en uso.  
  
 Si dispone de demasiados archivos de registro, podría ser un indicador de un problema de arquitectura con la aplicación. Consulte la documentación sobre la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> para más información.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> en <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> para incluir una marca de fecha en el nombre del archivo de registro.  
  
2. Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [My. Application. log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My. Application. info. DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
