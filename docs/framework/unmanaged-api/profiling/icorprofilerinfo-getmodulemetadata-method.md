---
title: "ICorProfilerInfo::GetModuleMetaData (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 540ed6f1f84f096563aa94798090c3511d6db5d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData (Método)
Obtiene una instancia de la interfaz de metadatos que se asigna para el módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo al que se asignará la instancia de interfaz.  
  
 `dwOpenFlags`  
 [in] Un valor de la [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeración que especifica el modo de abrir archivos de manifiesto. Solo el `ofRead`, `ofWrite` y `ofNoTransform` bits son válidos.  
  
 `riid`  
 [in] La referencia del identificador (GUID) de la interfaz de metadatos cuya instancia se va a recuperar. Vea [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) para obtener una lista de las interfaces.  
  
 `ppOut`  
 [out] Un puntero a la dirección de la instancia de la interfaz de metadatos.  
  
## <a name="remarks"></a>Comentarios  
 Se puede pedir a los metadatos que se abrirá en modo de lectura/escritura, pero esto dará como resultado de una ejecución más lenta de metadatos del programa, porque los cambios realizan en los metadatos no se puede optimizar como si fueran del compilador.  
  
 Algunos módulos (por ejemplo, los módulos de recursos) no tienen metadatos. En esos casos, `GetModuleMetaData` devolverá un valor HRESULT de S_FALSE y un valor null en *`ppOut`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
