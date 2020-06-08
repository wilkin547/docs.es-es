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
ms.openlocfilehash: f5438ddc655f0f6a7c11d978a47b1bf9e2a13059
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497015"
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
 El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de [metadatos](../metadata/index.md) para un módulo determinado. Después, el token de metadatos que se devuelve a la ubicación a la que `pToken` hace referencia puede usarse para acceder a los metadatos de la función.  
  
 El identificador de clase y los argumentos de tipo que se devuelven mediante los parámetros `pClassId` y `typeArgs` dependen del valor que se pasa en el parámetro `frameInfo`, como se muestra en la tabla siguiente.  
  
|Valor del parámetro `frameInfo`|Resultado|  
|----------------------------------------|------------|  
|Un valor `COR_PRF_FRAME_INFO` que se obtiene de una devolución de llamada `FunctionEnter2`|El `ClassID` que se devuelve en la ubicación a la que `pClassId` hace referencia y todos los argumentos de tipo que se devuelven en la matriz `typeArgs` serán exactos.|  
|Un valor `COR_PRF_FRAME_INFO` que se obtiene de un origen que no es una devolución de llamada `FunctionEnter2`|El `ClassID` y los argumentos de tipo no se puede determinar exactamente. Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.|  
|Cero|El `ClassID` y los argumentos de tipo no se puede determinar exactamente. Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.|  
  
 Después de que `GetFunctionInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`. Para ello, compare el valor al que `pcTypeArgs` apunta con el valor del parámetro `cTypeArgs`. Si `pcTypeArgs` apunta a un valor mayor que `cTypeArgs` dividido por el tamaño de un valor `ClassID`, asigne un búfer `pcTypeArgs` mayor, actualice `cTypeArgs` con el nuevo tamaño y vuelva a llamar a `GetFunctionInfo2`.  
  
 También tiene la opción de llamar primero a `GetFunctionInfo2` con un búfer `pcTypeArgs` de longitud de cero para obtener el tamaño de búfer correcto. Después, establezca el tamaño del búfer en el valor devuelto en `pcTypeArgs`, dividido por el tamaño de un valor `ClassID` y vuelva a llamar a `GetFunctionInfo2`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
