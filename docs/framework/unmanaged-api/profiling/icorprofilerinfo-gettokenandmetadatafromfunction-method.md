---
title: "ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 585b28161814045777cf2294f78bafc3229bfae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)
Obtiene el token de metadatos y una instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función para la que se va a obtener el token de metadatos y la interfaz de metadatos.  
  
 `riid`  
 [in] El identificador de referencia de la interfaz de metadatos para obtener la instancia de.  
  
 `ppImport`  
 [out] Un puntero a la dirección de la instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.  
  
 `pToken`  
 [out] Un puntero al token de metadatos para la función especificada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
