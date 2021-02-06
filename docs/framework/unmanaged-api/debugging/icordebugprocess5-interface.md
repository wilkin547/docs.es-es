---
description: 'Más información acerca de: interfaz ICorDebugProcess5'
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
ms.openlocfilehash: 880c305c1d9786f87d9727836a973696aa686ecf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649772"
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5 (Interfaz)

Extiende la interfaz ICorDebugProcess para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnableNGenPolicy](icordebugprocess5-enablengenpolicy-method.md)|Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.|  
|[Método EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md)|Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.|  
|[Método EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)|Obtiene un enumerador para los identificadores de objetos de un proceso.|  
|[Método EnumerateHeap](icordebugprocess5-enumerateheap-method.md)|Obtiene un enumerador para los objetos en el montón administrado.|  
|[Método EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md)|Obtiene un enumerador para las regiones del montón administrado.|  
|[Método GetArrayLayout](icordebugprocess5-getarraylayout-method.md)|Obtiene información sobre el diseño de una matriz en la memoria.|  
|[Método GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)|Obtiene un puntero a una estructura de [COR_HEAPINFO](cor-heapinfo-structure.md) que contiene información sobre los objetos que se van a recopilar en el montón administrado.|  
|[GetObject (Método)](icordebugprocess5-getobject-method.md)|Obtiene un puntero a un objeto en el montón administrado.|  
|[Método GetTypeFields](icordebugprocess5-gettypefields-method.md)|Obtiene un puntero a una matriz que contiene información de campo para un tipo basado en su identificador de tipo.|  
|[Método GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)|Obtiene un objeto de tipo que proporciona información sobre un objeto basándose en sus identificadores de tipo.|  
|[Método GetTypeID](icordebugprocess5-gettypeid-method.md)|Obtiene el identificador de tipo para el objeto en una dirección especificada.|  
|[Método GetTypeLayout](icordebugprocess5-gettypelayout-method.md)|Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.|  
  
## <a name="remarks"></a>Observaciones  

 Esta interfaz extiende lógicamente las interfaces ICorDebugProcess, ICorDebugProcess2 y [ICorDebugProcess3 (](icordebugprocess3-interface.md) .  
  
> [!NOTE]
> Esta interfaz no admite la llamada remota, ya sea desde otro equipo o desde otro proceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
