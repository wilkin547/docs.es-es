---
description: 'Más información sobre: ICorProfilerFunctionControl:: SetILInstrumentedCodeMap ((método)'
title: ICorProfilerFunctionControl::SetILInstrumentedCodeMap (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
ms.openlocfilehash: bb345f737459342e0146cbb0e0bd7dd4b1e9a037
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781550"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a>ICorProfilerFunctionControl::SetILInstrumentedCodeMap (Método)

Establece un mapa de código para la función especificada usando las entradas del mapa de Common Intermediate Language (CIL) especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cILMapEntries`  
 [in] Número de entradas en el mapa.  
  
 `rgILMapEntries`  
 [in] Matriz asignada por el llamante de entradas COR_IL_MAP. La interpretación de estas entradas es la misma que para el método [ICorProfilerInfo:: SetILInstrumentedCodeMap (](icorprofilerinfo-setilinstrumentedcodemap-method.md) .  
  
## <a name="remarks"></a>Observaciones  

 La configuración de la asignación mediante una llamada a este método permite que el depurador recupere la asignación mediante una llamada a [ICorDebugILCode2:: GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md). También permite al depurador usar la asignación internamente al calcular los desplazamientos del IL para los seguimientos de pila y la duración de las variables.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
