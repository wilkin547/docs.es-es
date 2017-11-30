---
title: ICorDebugValue2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue2
helpviewer_keywords: ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f74a90952c6ac780c53441af472faeb999febbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue2-interface"></a>ICorDebugValue2 (Interfaz)
Extiende la interfaz "ICorDebugValue" para proporcionar compatibilidad para objetos de "ICorDebugType".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetExactType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|Obtiene un puntero de interfaz a una `ICorDebugType` objeto que representa el <xref:System.Type> de este valor.|  
  
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
    
 [ICorDebugValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
