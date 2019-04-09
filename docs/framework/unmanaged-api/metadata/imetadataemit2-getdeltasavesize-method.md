---
title: IMetaDataEmit2::GetDeltaSaveSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69897a7b646eb9f58e6b38588e302287b4241779
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139898"
---
# <a name="imetadataemit2getdeltasavesize-method"></a>IMetaDataEmit2::GetDeltaSaveSize (Método)
Obtiene un valor que indica cualquier cambio en el tamaño de los metadatos que da como resultado de la sesión actual de editar y continuar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fSave`  
 [in] Uno de los [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) valores, que indica el nivel de precisión deseado. Para la versión 2.0 de .NET Framework, se omite este parámetro.  
  
 `pdwSaveSize`  
 [out] El cambio en el tamaño de los metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
