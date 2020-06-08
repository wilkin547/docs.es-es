---
title: ICorProfilerFunctionEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
ms.openlocfilehash: df62ad1af0ea91783cb62bb0590b6e36d812de3a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503073"
---
# <a name="icorprofilerfunctionenumnext-method"></a>ICorProfilerFunctionEnum::Next (Método)
Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 [in] Número de funciones para recuperar.  
  
 `ids`  
 [out] Matriz de valores `COR_PRF_FUNCTION`, cada uno de los cuales representa una función recuperada.  
  
 `pceltFetched`  
 [out] Puntero al número de funciones realmente devueltos en la matriz `ids`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|Se devolvieron `celt` elementos.|  
|S_FALSE|Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerFunctionEnum (Interfaz)](icorprofilerfunctionenum-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
