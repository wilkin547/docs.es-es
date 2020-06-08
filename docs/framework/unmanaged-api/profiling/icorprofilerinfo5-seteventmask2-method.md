---
title: ICorProfilerInfo5::SetEventMask2 (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 8027cdcde8281c363207e309bf65fcd90c03b626
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495637"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a>ICorProfilerInfo5::SetEventMask2 (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR). Proporciona más funcionalidad que el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwEventsLow`  
 [in] Valor de 4 bytes que especifica las categorías de eventos. Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 `dwEventsHigh`  
 [in] Valor de 4 bytes que especifica las categorías de eventos.  Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Comentarios  
 El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles. Normalmente, se llama al método [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) para determinar qué bits se establecen, se realiza una operación OR lógica de sus `pdwEventsLow` `pdwEventsHigh` valores y y los bits nuevos que se desea establecer y, después, se llama al `SetEventMask2` método.  
  
 Este método es la alternativa recomendada al método [SetEventMask](icorprofilerinfo-seteventmask-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo5 (Interfaz)](icorprofilerinfo5-interface.md)
- [GetEventMask2 (método)](icorprofilerinfo5-geteventmask2-method.md)
