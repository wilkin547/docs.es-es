---
title: "ICorProfilerInfo5::SetEventMask2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: IcorProfilerInfo5.SetEventMask2
api_location: mscorwks.dll
api_type: COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2cf383ef8100e096b8373b59231d4aef12725c3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo5seteventmask2-method"></a>ICorProfilerInfo5::SetEventMask2 (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR). Proporciona más funcionalidad que la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwEventsLow`  
 [in] Valor de 4 bytes que especifica las categorías de eventos. Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.  
  
 `dwEventsHigh`  
 [in] Valor de 4 bytes que especifica las categorías de eventos.  Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeración.  
  
## <a name="remarks"></a>Comentarios  
 El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles. Normalmente, se llama a la [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) método para determinar qué bits se establecen, realizar una operación lógica OR de sus `pdwEventsLow` y `pdwEventsHigh` valores y los nuevos bits que desea establecer y, a continuación, llame a la `SetEventMask2` método.  
  
 Este método es la alternativa recomendada para la [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo5 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [GetEventMask2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
