---
title: ICorProfilerInfo2::GetFunctionInfo2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type:
- apiref
ms.openlocfilehash: 11f9a186f5ec5e3b9e718a3ccd43b35b66d28078
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433179"
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a>ICorProfilerInfo2::GetFunctionInfo2 (Método)
Obtiene la clase primaria, el token de metadatos y el `ClassID` de cada argumento de tipo, si está presente, de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `funcId`  
 [in] Identificador de la función para la que se va a obtener la clase primaria y otra información.  
  
 `frameInfo`  
 [in] Valor `COR_PRF_FRAME_INFO` que apunta a información acerca de un marco de pila.  
  
 `pClassId`  
 [out] Puntero a la clase primaria de la función.  
  
 `pModuleId`  
 [out] Puntero al módulo en el que se define la clase primaria de la función.  
  
 `pToken`  
 [out] Puntero al token de metadatos para la función.  
  
 `cTypeArgs`  
 [in] Tamaño de la matriz `typeArgs`.  
  
 `pcTypeArgs`  
 [out] Puntero al número total de valores `ClassID`.  
  
 `typeArgs`  
 [out] Matriz de valores `ClassID`, cada uno de los cuales es el identificador de un argumento de tipo de la función. Cuando el método vuelve, `typeArgs` contendrá algunos o todos los valores `ClassID`.  
  
## <a name="remarks"></a>Comentarios  
 The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module. Después, el token de metadatos que se devuelve a la ubicación a la que `pToken` hace referencia puede usarse para acceder a los metadatos de la función.  
  
 El identificador de clase y los argumentos de tipo que se devuelven mediante los parámetros `pClassId` y `typeArgs` dependen del valor que se pasa en el parámetro `frameInfo`, como se muestra en la tabla siguiente.  
  
|Valor del parámetro `frameInfo`|Resultado|  
|----------------------------------------|------------|  
|Un valor `COR_PRF_FRAME_INFO` que se obtiene de una devolución de llamada `FunctionEnter2`|El `ClassID` que se devuelve en la ubicación a la que `pClassId` hace referencia y todos los argumentos de tipo que se devuelven en la matriz `typeArgs` serán exactos.|  
|Un valor `COR_PRF_FRAME_INFO` que se obtiene de un origen que no es una devolución de llamada `FunctionEnter2`|El `ClassID` y los argumentos de tipo no se puede determinar exactamente. Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.|  
|Cero|El `ClassID` y los argumentos de tipo no se puede determinar exactamente. Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.|  
  
 Después de que `GetFunctionInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`. Para ello, compare el valor al que `pcTypeArgs` apunta con el valor del parámetro `cTypeArgs`. Si `pcTypeArgs` apunta a un valor mayor que `cTypeArgs` dividido por el tamaño de un valor `ClassID`, asigne un búfer `pcTypeArgs` mayor, actualice `cTypeArgs` con el nuevo tamaño y vuelva a llamar a `GetFunctionInfo2`.  
  
 También tiene la opción de llamar primero a `GetFunctionInfo2` con un búfer `pcTypeArgs` de longitud de cero para obtener el tamaño de búfer correcto. Después, establezca el tamaño del búfer en el valor devuelto en `pcTypeArgs`, dividido por el tamaño de un valor `ClassID` y vuelva a llamar a `GetFunctionInfo2`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
