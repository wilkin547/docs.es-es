---
description: 'Más información acerca de: enumeración COR_PRF_EVENT_DATA'
title: Enumeración COR_PRF_EVENT_DATA
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENT_DATA
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 477f36476deb9c0d74e263703e36b134c91b5327
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805575"
---
# <a name="cor_prf_event_data-enumeration"></a>Enumeración COR_PRF_EVENT_DATA

Describe los datos de evento para un evento EventPipe que se está escribiendo.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct
{
    UINT64 ptr;
    UINT32 size;
    UINT32 reserved;
} COR_PRF_EVENT_DATA;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ptr`|Puntero a los datos.|  
|`size`|Tamaño de los datos a los que apunta `ptr` .|  
|`reserved`|Un campo específico de implementación reservado.|  
  
## <a name="remarks"></a>Observaciones  

 El `COR_PRF_EVENT_DATA` método [ICorProfilerInfo12:: EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md) usa la estructura para providate la carga de datos para el evento que se va a escribir.
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md)
