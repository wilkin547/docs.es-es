---
title: ICorDebugMDA (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA
helpviewer_keywords: ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00a003ee060de59fe0eb8ce8f740a620d77a7c85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA (Interfaz)
Representa un mensaje del asistente para la depuración administrada (MDA).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetDescription (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Obtiene una cadena que contiene una descripción de este MDA.|  
|[GetFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Obtiene las marcas asociadas a este MDA.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Obtiene una cadena que contiene el nombre de este MDA.|  
|[GetOSThreadId (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Obtiene el identificador de subproceso de sistema operativo en el que se está ejecutando este MDA.|  
|[GetXML (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Obtiene la secuencia XML completa asociada a este MDA.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
