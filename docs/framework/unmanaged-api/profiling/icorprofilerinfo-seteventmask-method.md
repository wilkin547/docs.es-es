---
title: ICorProfilerInfo::SetEventMask (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
ms.openlocfilehash: b79668130570dc69a580fbf7da4dc122389d9ef0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136696"
---
# <a name="icorprofilerinfoseteventmask-method"></a>ICorProfilerInfo::SetEventMask (Método)
Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones desde Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwEvents`  
 [in] Valor de 4 bytes que especifica las categorías de eventos. Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Debe llamar al método [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) en lugar de a este método. Aunque el método de `SetEventMask` se sigue admitiendo, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) proporciona funcionalidad adicional.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [SetEventMask2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
