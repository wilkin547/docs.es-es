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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 343cedcf26112f0f2bcc7943ea5ee9f302329a15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs (Método)
Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, que contiene la clase, y `ClassID` valores de cualquier tipo de argumentos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El identificador del módulo en el que reside la función.  
  
 `funcDef`  
 [in] Un `mdMethodDef` símbolo (token) de metadatos que hace referencia a la función.  
  
 `classId`  
 [in] El identificador de clase contenedora de la función.  
  
 `cTypeArgs`  
 [in] El número de parámetros de tipo para la función especificada. Este valor debe ser cero para las funciones no genéricas.  
  
 `typeArgs`  
 [in] Una matriz de `ClassID` valores, cada uno de los cuales es un argumento de la función. El valor de `typeArgs` puede ser NULL si `cTypeArgs` se establece en cero.  
  
 `pFunctionID`  
 [out] Un puntero a la `FunctionID` de la función especificada.  
  
## <a name="remarks"></a>Comentarios  
 Llamar a la `GetFunctionFromTokenAndTypeArgs` método con un `mdMethodRef` metadatos en lugar de un `mdMethodDef` símbolo (token) de metadatos puede tener resultados imprevisibles. Los llamadores deben resolver el `mdMethodRef` para un `mdMethodDef` al pasarla.  
  
 Si la función ya no está cargada, la llamada a `GetFunctionFromTokenAndTypeArgs` hará que la carga que se produzca, que es una operación peligrosa en muchos contextos. Por ejemplo, llamar a este método durante la carga de módulos o tipos podría provocar un bucle infinito como el tiempo de ejecución intenta la carga circular.  
  
 En general, uso de `GetFunctionFromTokenAndTypeArgs` se desaconseja. Si los generadores de perfiles están interesados en los eventos de una función en particular, debe almacenar el `ModuleID` y `mdMethodDef` de esa función y el uso [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) para comprobar si un determinado `FunctionID` es que la función deseada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
