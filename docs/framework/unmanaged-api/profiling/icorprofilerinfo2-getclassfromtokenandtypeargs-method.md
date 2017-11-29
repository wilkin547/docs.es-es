---
title: "ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 332be5616ac11fc89df8c8d54aa5c0cbc49491ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)
Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y la `ClassID` valores de cualquier tipo de argumentos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El identificador del módulo en el que reside el tipo.  
  
 `typeDef`  
 [in] Un `mdTypeDef` símbolo (token) de metadatos que hace referencia al tipo.  
  
 `cTypeArgs`  
 [in] El número de parámetros de tipo para el tipo dado. Este valor debe ser cero para tipos no genéricos.  
  
 `typeArgs`  
 [in] Una matriz de `ClassID` valores, cada uno de los cuales es un argumento del tipo. El valor de `typeArgs` puede ser NULL si `cTypeArgs` se establece en cero.  
  
 `pClassID`  
 [out] Un puntero a la `ClassID` del tipo especificado.  
  
## <a name="remarks"></a>Comentarios  
 Llamar a la `GetClassFromTokenAndTypeArgs` método con un `mdTypeRef` en lugar de un `mdTypeDef` símbolo (token) de metadatos puede tener resultados imprevisibles; los llamadores deben resolver el `mdTypeRef` para un `mdTypeDef` al pasarla.  
  
 Si ya no se carga el tipo, una llamada a `GetClassFromTokenAndTypeArgs` se desencadena la carga, que es una operación peligrosa en muchos contextos. Por ejemplo, llamar a este método durante la carga de módulos u otros tipos podría provocar un bucle infinito como el tiempo de ejecución intenta la carga circular.  
  
 En general, uso de `GetClassFromTokenAndTypeArgs` se desaconseja. Si los generadores de perfiles están interesados en los eventos de un tipo determinado, debe almacenar el `ModuleID` y `mdTypeDef` de ese tipo y el uso [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) para comprobar si un determinado `ClassID` es el de la tipo deseado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
