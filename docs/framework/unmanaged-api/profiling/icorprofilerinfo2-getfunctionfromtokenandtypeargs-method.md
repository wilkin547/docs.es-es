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
ms.openlocfilehash: 7e1498ec3ce1e5258546cec8d8f8172739af6d9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756148"
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
  
## <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El identificador del módulo en el que reside la función.  
  
 `funcDef`  
 [in] Un `mdMethodDef` token de metadatos que hace referencia a la función.  
  
 `classId`  
 [in] El identificador de la clase contenedora de la función.  
  
 `cTypeArgs`  
 [in] El número de parámetros de tipo para la función especificada. Este valor debe ser cero para las funciones no genéricos.  
  
 `typeArgs`  
 [in] Una matriz de `ClassID` valores, cada uno de los cuales es un argumento de la función. El valor de `typeArgs` puede ser NULL si `cTypeArgs` se establece en cero.  
  
 `pFunctionID`  
 [out] Un puntero a la `FunctionID` de la función especificada.  
  
## <a name="remarks"></a>Comentarios  
 Una llamada a la `GetFunctionFromTokenAndTypeArgs` método con un `mdMethodRef` metadatos en lugar de un `mdMethodDef` token de metadatos puede tener resultados impredecibles. Los llamadores deben resolver el `mdMethodRef` a un `mdMethodDef` al pasarlo.  
  
 Si la función ya no está cargada, al llamar a `GetFunctionFromTokenAndTypeArgs` hará que la carga que se produzca, que es una operación peligrosa en muchos contextos. Por ejemplo, llamar a este método durante la carga de módulos o tipos podría provocar un bucle infinito mientras el tiempo de ejecución intenta la carga circular.  
  
 En general, uso de `GetFunctionFromTokenAndTypeArgs` es en absoluto. Si los generadores de perfiles están interesados en eventos para una función determinada, debe almacenar el `ModuleID` y `mdMethodDef` de esa función y el uso [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) para comprobar si un determinado `FunctionID` es que el de la función deseada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
