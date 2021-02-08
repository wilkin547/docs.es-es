---
description: 'Más información acerca de: ICorProfilerInfo:: Gettokenandmetadatafromfunction ((método)'
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
ms.openlocfilehash: 0cea6564df15c7a7f4c46097714cc0956002599b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783851"
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

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
