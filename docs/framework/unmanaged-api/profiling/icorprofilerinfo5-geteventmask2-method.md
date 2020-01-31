---
title: ICorProfilerInfo5::GetEventMask2 (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: f3943eef969f777b40dc51c4900b190561f14887
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868400"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>ICorProfilerInfo5::GetEventMask2 (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de Common Language Runtime (CLR).  Proporciona funcionalidad no proporcionada por el método [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pdwEventsLow`  
 [out] Puntero a un valor de 4 bytes que especifica las categorías de eventos. Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 `pdwEventsHigh`  
 [out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.  Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente. Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .  
  
## <a name="remarks"></a>Notas  
 El método `GetEventMask2` se usa para determinar a qué devoluciones de llamada se ha suscrito el generador de perfiles. Normalmente, se realiza una operación OR lógica de los valores `pdwEventsLow` y `pdwEventsHigh` y los bits nuevos que se desea establecer y, después, se llama al método [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
 Este método es la alternativa recomendada para el método [GetEventMask (](icorprofilerinfo-geteventmask-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo5 (interfaz)](icorprofilerinfo5-interface.md)
- [SetEventMask2 (método)](icorprofilerinfo5-seteventmask2-method.md)
