---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433215"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)
Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, la clase contenedora y los valores de `ClassID` de cualquier argumento de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleID`  
 de IDENTIFICADOR del módulo en el que reside la función.  
  
 `funcDef`  
 de Un token de metadatos de `mdMethodDef` que hace referencia a la función.  
  
 `classId`  
 de IDENTIFICADOR de la clase contenedora de la función.  
  
 `cTypeArgs`  
 de El número de parámetros de tipo para la función especificada. Este valor debe ser cero para las funciones no genéricas.  
  
 `typeArgs`  
 de Matriz de valores de `ClassID`, cada uno de los cuales es un argumento de la función. El valor de `typeArgs` puede ser NULL si `cTypeArgs` está establecido en cero.  
  
 `pFunctionID`  
 enuncia Puntero al `FunctionID` de la función especificada.  
  
## <a name="remarks"></a>Comentarios  
 Llamar al método `GetFunctionFromTokenAndTypeArgs` con un `mdMethodRef` metadatos en lugar de un token de metadatos de `mdMethodDef` puede tener resultados imprevisibles. Los llamadores deben resolver el `mdMethodRef` en un `mdMethodDef` al pasarlo.  
  
 Si la función no está cargada todavía, la llamada a `GetFunctionFromTokenAndTypeArgs` provocará que se produzca la carga, lo que es una operación peligrosa en muchos contextos. Por ejemplo, llamar a este método durante la carga de módulos o tipos podría provocar un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.  
  
 En general, no se recomienda el uso de `GetFunctionFromTokenAndTypeArgs`. Si los perfiles están interesados en eventos para una función determinada, deben almacenar los `ModuleID` y `mdMethodDef` de esa función y usar [ICorProfilerInfo2:: getfunctioninfo2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) para comprobar si un `FunctionID` determinado es el de la función deseada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
