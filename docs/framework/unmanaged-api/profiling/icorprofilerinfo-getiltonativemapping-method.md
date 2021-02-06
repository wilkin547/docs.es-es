---
description: 'Más información sobre: ICorProfilerInfo:: GetILToNativeMapping (método)'
title: ICorProfilerInfo::GetILToNativeMapping (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: ce3473365eb98beca4d2e9116251200d7539e4c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647393"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a>ICorProfilerInfo::GetILToNativeMapping (Método)

Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la función especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `functionId`  
 [in] Identificador de la función que contiene el código.  
  
 `cMap`  
 [in] Tamaño máximo de la matriz `map`.  
  
 `pcMap`  
 [out] Número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.  
  
 `map`  
 [out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos. Después de que el método `GetILToNativeMapping` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.  
  
## <a name="remarks"></a>Observaciones  

 El método `GetILToNativeMapping` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`. Para transmitir que ciertos intervalos de instrucciones nativas se corresponden con regiones especiales de código (por ejemplo, el prólogo), una entrada de la matriz puede tener su `ilOffset` campo establecido en un valor de la enumeración [CorDebugIlToNativeMappingTypes (](../debugging/cordebugiltonativemappingtypes-enumeration.md) .  
  
 Después de la devolución de `GetILToNativeMapping`, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`. Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`. Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping`.  
  
 También tiene la opción de llamar primero a `GetILToNativeMapping` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [Método GetILToNativeMapping2](icorprofilerinfo4-getiltonativemapping2-method.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
