---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeGetProviderInfo (método)'
title: 'ICorProfilerInfo12:: EventPipeGetProviderInfo (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeGetProviderInfo
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7bc7ffe1c31e88dc1c65f1670f9bd179e732abfe
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805706"
---
# <a name="icorprofilerinfo12eventpipegetproviderinfo-method"></a>ICorProfilerInfo12:: EventPipeGetProviderInfo (método)

Crea un proveedor EventPipe que el generador de perfiles puede usar para escribir eventos para que los reciban otros agentes de escucha de EventPipe.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT EventPipeGetProviderInfo(
                [in] EVENTPIPE_PROVIDER provider,
                [in]  ULONG      cchName,
                [out] ULONG      *pcchName,
                [out, annotation("_Out_writes_to_(cchName, *pcchName)")]
                      WCHAR      providerName[]);
```  
  
## <a name="parameters"></a>Parámetros

`provider` de IDENTIFICADOR del proveedor para el que se va a proporcionar el nombre.

`cchName` de Tamaño, en caracteres, de `providerName` .

`pcchName` enuncia Puntero a la longitud total de caracteres de `providerName` .

`providerName` enuncia Un llamador proporcionó un búfer de caracteres anchos. Cuando la función devuelva el búfer contendrá el nombre del proveedor.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Información general sobre EventPipe](../../../core/diagnostics/eventpipe.md)
- [EventProviders conocidos](../../../core/diagnostics/well-known-event-providers.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
