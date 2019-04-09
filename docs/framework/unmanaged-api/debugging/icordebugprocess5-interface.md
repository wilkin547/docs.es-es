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
ms.openlocfilehash: b5904083be66d4bd6dc69729bebc28db8a800e77
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089243"
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5 (Interfaz)
Extiende la interfaz ICorDebugProcess para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de objetos administrados, y determinar si un depurador carga imágenes desde la caché de imágenes nativas local de la aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnableNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.|  
|[Método EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Obtiene un enumerador para todos los objetos que se van a recopilar los elementos no utilizados en un proceso.|  
|[Método EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Obtiene un enumerador para los identificadores de objeto en un proceso.|  
|[Método EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Obtiene un enumerador para los objetos del montón administrado.|  
|[Método EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Obtiene un enumerador para las regiones del montón administrado.|  
|[Método GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Obtiene información sobre el diseño de una matriz en la memoria.|  
|[Método GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Obtiene un puntero a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) estructura que contiene información acerca de los objetos que van a recopilar los elementos no utilizados en el montón administrado.|  
|[GetObject (Método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Obtiene un puntero a un objeto en el montón administrado.|  
|[Método GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Obtiene un puntero a una matriz que contiene información de campo para un tipo según su identificador de tipo.|  
|[Método GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Obtiene un objeto de tipo que proporciona información sobre un objeto según sus identificadores de tipo.|  
|[Método GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Obtiene el identificador de tipo para el objeto en una dirección especificada.|  
|[Método GetTypeLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Obtiene información sobre el diseño de un objeto en memoria en función de su identificador de tipo.|  
  
## <a name="remarks"></a>Comentarios  
 Esta interfaz extiende lógicamente la ICorDebugProcess, ICorDebugProcess2, y [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.  
  
> [!NOTE]
>  Esta interfaz no es compatible con la que se va a llamar de forma remota, desde otro equipo o desde otro proceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
