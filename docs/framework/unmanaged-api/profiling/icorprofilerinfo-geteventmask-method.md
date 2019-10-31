---
title: ICorProfilerInfo::GetEventMask (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
ms.openlocfilehash: f6a4ee32d1f0bd6f66b2cd2249dd90522062cdab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120950"
---
# <a name="icorprofilerinfogeteventmask-method"></a>ICorProfilerInfo::GetEventMask (Método)
Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de eventos para Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwEvents`  
 [out] Puntero a un valor de 4 bytes que especifica las categorías de eventos. Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Debe llamar al método [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) en lugar de a este método. Aunque el método de `SetEventMask` se sigue admitiendo, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) proporciona funcionalidad adicional.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetEventMask2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
