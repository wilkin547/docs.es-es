---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973815"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)
  
 Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.   
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función cuyas direcciones de inicio de código nativo deben devolverse.  
  
 `reJitId`  
 [in] Identidad de la función recompilada con JIT. 
  
 `cCodeStartAddresses` \
 [in] Tamaño máximo de la matriz `codeStartAddresses`.

 `pcCodeStartAddresses` \
 enuncia El número de direcciones disponibles.

 `codeStartAddresses` \
 enuncia Una matriz de `UINT_PTR`, cada una de las cuales es la dirección inicial de un cuerpo nativo para la función especificada. 

## <a name="remarks"></a>Comentarios  
 Cuando la compilación en capas está habilitada, una función puede tener más de un cuerpo de código nativo. 

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>Vea también
- [Interfaz ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

