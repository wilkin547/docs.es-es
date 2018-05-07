---
title: ICorDebugProcess5 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3aed85e989313e4778e12a6f6bb789ccef49747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5 (Interfaz)
Extiende la interfaz ICorDebugProcess que admitan el acceso al montón administrado, para proporcionar información sobre la recolección de los objetos administrados, y determinar si un depurador carga imágenes desde la caché de imágenes nativas local de la aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnableNGenPolicy (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Establece un valor que determina la forma en que una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.|  
|[EnumerateGCReferences (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Obtiene un enumerador para todos los objetos que se recolectarán como elementos no utilizados en un proceso.|  
|[EnumerateHandles (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Obtiene un enumerador para los identificadores de objeto en un proceso.|  
|[EnumerateHeap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Obtiene un enumerador para los objetos del montón administrado.|  
|[EnumerateHeapRegions (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Obtiene un enumerador para las regiones del montón administrado.|  
|[GetArrayLayout (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Obtiene información sobre el diseño de una matriz en la memoria.|  
|[GetGCHeapInformation (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Obtiene un puntero a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) estructura que contiene información acerca de los objetos que se recolectarán como elementos no utilizados en el montón administrado.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Obtiene un puntero a un objeto en el montón administrado.|  
|[GetTypeFields (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Obtiene un puntero a una matriz que contiene información de campo para un tipo basándose en su identificador de tipo.|  
|[GetTypeForTypeID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Obtiene un objeto de tipo que proporciona información sobre un objeto basándose en sus identificadores de tipo.|  
|[GetTypeID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Obtiene el identificador de tipo para el objeto en una dirección especificada.|  
|[GetTypeLayout (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Obtiene información sobre el diseño de un objeto en la memoria basándose en su identificador de tipo.|  
  
## <a name="remarks"></a>Comentarios  
 Esta interfaz extiende lógicamente la ICorDebugProcess, ICorDebugProcess2, y [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.  
  
> [!NOTE]
>  Esta interfaz no admite que se llame de forma remota, desde otro equipo o desde otro proceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
