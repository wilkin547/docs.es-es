---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_PROVIDER_CONFIG'
title: Enumeración COR_PRF_EVENTPIPE_PROVIDER_CONFIG
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PROVIDER_CONFIG
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 2a7a5e720e9468b44e6504d24a3b9ad836e13693
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805849"
---
# <a name="cor_prf_eventpipe_provider_config-enumeration"></a>Enumeración COR_PRF_EVENTPIPE_PROVIDER_CONFIG

Describe los campos necesarios para configurar un proveedor de EventPipe.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct
{
    const WCHAR* providerName;
    UINT64       keywords;
    UINT32       loggingLevel;
    const WCHAR* filterData;
} COR_PRF_EVENTPIPE_PROVIDER_CONFIG;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`providerName`|Nombre del proveedor que se va a habilitar.|  
|`keywords`|Palabras clave que se van a habilitar en el proveedor.|  
|`loggingLevel`|Nivel que se va a habilitar en el proveedor.|  
|`filterData`|Una cadena de caracteres anchos que contiene el filterdata que se va a usar al habilitar el proveedor.|  
  
## <a name="remarks"></a>Observaciones  

 El `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` método [ICorProfilerInfo12:: EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md) usa la estructura para indicar la configuración del proveedor que se va a agregar a la sesión.
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
