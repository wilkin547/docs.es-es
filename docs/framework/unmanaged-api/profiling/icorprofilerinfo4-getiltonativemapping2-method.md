---
title: ICorProfilerInfo4::GetILToNativeMapping2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fba81500749a16a59405edaaa2ee1d12d86229f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461716"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a>ICorProfilerInfo4::GetILToNativeMapping2 (Método)
Obtiene una asignación de desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código incluido en la versión recompilada con JIT de la función especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] Identificador de la función que contiene el código.  
  
 `pReJitId`  
 [in] Identidad de la función recompilada con JIT. La identidad debe ser cero en [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
 `cMap`  
 [in] Tamaño máximo de la matriz `map`.  
  
 `pcMap`  
 [out] El número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.  
  
 `map`  
 [out] Matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales especifica los desplazamientos. Después de que el método `GetILToNativeMapping2` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.  
  
## <a name="remarks"></a>Comentarios  
 `GetILToNativeMapping2` es similar a la [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) método, salvo que permite al generador de perfiles especificar el identificador de la función recompilada en futuras versiones.  
  
> [!NOTE]
>  El [icorprofilerfunctioncontrol:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) método no se implementa en el [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], por lo que las funciones que se han recompilado con JIT no pueden tener una asignación de IL a nativo diferente de la originalmente función compilada. Por lo tanto, no se puede llamar a `GetILToNativeMapping2` con un identificador compilado con JIT distinto de cero en [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
 El método `GetILToNativeMapping2` devuelve una matriz de estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`. Para indicar que algunos intervalos de instrucciones nativas se corresponden con regiones de código (por ejemplo, el prólogo) especiales, puede tener una entrada en la matriz su `ilOffset` campo establecido en un valor de la [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeración.  
  
 Después de que `GetILToNativeMapping2` vuelva, debe comprobar que el búfer `map` era lo suficientemente grande como para contener todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`. Para ello, compare el valor de `cMap` con el valor del parámetro `pcMap`. Si el valor de `pcMap`, al multiplicarlo por el tamaño de una estructura `COR_DEBUG_IL_TO_NATIVE_MAP`, es mayor que `cMap`, asigne un búfer `map` mayor, actualice `cMap` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetILToNativeMapping2`.  
  
 También puede llamar primero a `GetILToNativeMapping2` con un búfer `map` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer en el valor devuelto en `pcMap` y volver a llamar a `GetILToNativeMapping2`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [GetILToNativeMapping (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
