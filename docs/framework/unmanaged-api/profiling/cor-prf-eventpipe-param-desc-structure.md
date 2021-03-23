---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_PARAM_DESC'
title: Enumeración COR_PRF_EVENTPIPE_PARAM_DESC
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_DESC
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: b23897580092cc9f3f887a21e86f7111fecd9f19
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805797"
---
# <a name="cor_prf_eventpipe_param_desc-enumeration"></a>Enumeración COR_PRF_EVENTPIPE_PARAM_DESC

Describe el nombre y el tipo de parámetro de un evento EventPipe.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct
{
    UINT32       type;
    UINT32       elementType;
    const WCHAR *name;
} COR_PRF_EVENTPIPE_PARAM_DESC;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`type`|Tipo del parámetro.|  
|`elementType`|El tipo de elemento si este parámetro es un tipo de matriz.|  
|`name`|Una cadena de caracteres anchos que contiene el nombre del parámetro.|  
  
## <a name="remarks"></a>Observaciones  

 El `COR_PRF_EVENTPIPE_PARAM_DESC` método [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) usa la estructura para definir los tipos de parámetro del evento que se está definiendo.
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md)
