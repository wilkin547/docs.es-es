---
title: ICorDebugILCode2::GetInstrumentedILMap (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4197b018ea85402762a8591b40f3503c02af3974
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673138"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>ICorDebugILCode2::GetInstrumentedILMap (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Devuelve la correspondencia entre los desplazamientos del lenguaje intermedio instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 cMap  
 [in] Capacidad de almacenamiento de la matriz `map`. Vea la sección Comentarios para obtener más información.  
  
 pcMap  
 [out] El número de valores COR_IL_MAP escritos en la matriz de asignaciones.  
  
 map  
 [out] Una matriz de valores COR_IL_MAP que proporcionan información sobre las asignaciones de IL instrumentado del generador de perfiles al IL del método original.  
  
## <a name="remarks"></a>Comentarios  
 Si el generador de perfiles establece la asignación mediante una llamada a la [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) método, el depurador puede llamar a este método para recuperar la asignación y usar la asignación internamente al calcular IL los desplazamientos de pila los seguimientos y duración de las variables.  
  
 Si `cMap` es 0 y `pcMap` no es**null**, `pcMap` se establece en el número de valores COR_IL_MAP disponibles. Si `cMap` no es cero, representa la capacidad de almacenamiento de la matriz `map`. Cuando el método vuelve, `map` contiene un máximo de `cMap` elementos, y `pcMap` se establece en el número de valores COR_IL_MAP escritos realmente en el `map` matriz.  
  
 Si el IL no se ha instrumentado o un generador de perfiles no ha proporcionado la asignación, este método devuelve `S_OK` y establece `pcMap` en 0.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
