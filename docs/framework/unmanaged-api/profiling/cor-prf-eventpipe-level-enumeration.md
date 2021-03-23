---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_LEVEL'
title: Enumeración COR_PRF_EVENTPIPE_LEVEL
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_LEVEL
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: da8211da1a9bb6262b078c5e56bee1d0c1f9342e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805823"
---
# <a name="cor_prf_eventpipe_level-enumeration"></a>Enumeración COR_PRF_EVENTPIPE_LEVEL

Describe el nivel de un evento EventPipe.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_LOGALWAYS = 0,
    COR_PRF_EVENTPIPE_CRITICAL = 1,
    COR_PRF_EVENTPIPE_ERROR = 2,
    COR_PRF_EVENTPIPE_WARNING = 3,
    COR_PRF_EVENTPIPE_INFORMATIONAL = 4,
    COR_PRF_EVENTPIPE_VERBOSE = 5
} COR_PRF_EVENTPIPE_LEVEL;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_LOGALWAYS`|El evento siempre se registra.|
|`COR_PRF_EVENTPIPE_CRITICAL`|El evento representa un mensaje crítico.|
|`COR_PRF_EVENTPIPE_ERROR`|El evento representa un mensaje de error.|
|`COR_PRF_EVENTPIPE_WARNING`|El evento representa un mensaje de advertencia.|
|`COR_PRF_EVENTPIPE_INFORMATIONAL`|El evento representa un mensaje informativo.|
|`COR_PRF_EVENTPIPE_VERBOSE`|El evento representa un mensaje detallado.|
  
## <a name="remarks"></a>Observaciones  

 El `COR_PRF_EVENTPIPE_LEVEL` método [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) usa la enumeración para indicar el nivel del evento que se está definiendo.
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md)
