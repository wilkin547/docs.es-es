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
ms.openlocfilehash: c6fdb7040620bb7a5b6aea6e0dc41e08d6f346d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210363"
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
 [in] Capacidad de almacenamiento de la matriz `map`. Para obtener más información, vea la sección Comentarios.  
  
 pcMap  
 [out] Número de valores COR_IL_MAP que se escriben en la matriz de asignaciones.  
  
 map  
 [out] Matriz de valores COR_IL_MAP que proporcionan información sobre las asignaciones del IL instrumentado del generador de perfiles al IL del método original.  
  
## <a name="remarks"></a>Observaciones  
 Si el generador de perfiles establece la asignación llamando al método [ICorProfilerInfo:: SetILInstrumentedCodeMap (](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , el depurador puede llamar a este método para recuperar la asignación y usar la asignación internamente al calcular los desplazamientos de Il para los seguimientos de la pila y la duración de las variables.  
  
 Si `cMap` es 0 y `pcMap` no es**null**, `pcMap` se establece en el número de valores de COR_IL_MAP disponibles. Si `cMap` no es cero, representa la capacidad de almacenamiento de la matriz `map`. Cuando el método vuelve, `map` contiene un máximo de `cMap` elementos y `pcMap` se establece en el número de valores COR_IL_MAP escritos realmente en la `map` matriz.  
  
 Si el IL no se ha instrumentado o un generador de perfiles no ha proporcionado la asignación, este método devuelve `S_OK` y establece `pcMap` en 0.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2 (Interfaz)](icordebugilcode2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
