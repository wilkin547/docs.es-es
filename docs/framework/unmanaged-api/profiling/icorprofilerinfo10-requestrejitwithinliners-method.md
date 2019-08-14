---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 79a1c80f1c7582bd0751c43dea1d35a4d4d1c661
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973985"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>ICorProfilerInfo10:: RequestReJITWithInliners (método)
  
ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.   
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```  
  
#### <a name="parameters"></a>Parámetros  
 
 `dwRejitFlags` \
 de Máscara de [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).
 
 `cFunctions`  
 [in] Número de funciones que se va a recompilar.  
  
 `moduleIds`  
 [in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.  
  
 `methodIds`  
 [in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.  

## <a name="remarks"></a>Comentarios  
  [Requestrejit (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) no realiza ningún seguimiento de los métodos insertados. Se espera que el generador de perfiles bloquee la inserción o realice un seguimiento `RequestReJIT` de la inserción y llame a para todos los inlineers para asegurarse de que se ReJITted cada instancia de un método insertado. Esto supone un problema con ReJIT en attach, ya que el generador de perfiles no está presente para supervisar la inserción. Se puede llamar a este método para garantizar que el conjunto completo de inlineers también se ReJITted.  

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]
  
## <a name="see-also"></a>Vea también
- [Interfaz ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

