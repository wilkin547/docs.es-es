---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
ms.openlocfilehash: b3e14230888e9bf846879d5728c2b20883fb8d53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438740"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)
Obtiene el token de metadatos y una instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función para la que se va a obtener el token de metadatos y la interfaz de metadatos.  
  
 `riid`  
 de IDENTIFICADOR de referencia de la interfaz de metadatos de la que se va a obtener la instancia.  
  
 `ppImport`  
 enuncia Puntero a la dirección de la instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.  
  
 `pToken`  
 enuncia Puntero al símbolo (token) de metadatos para la función especificada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
