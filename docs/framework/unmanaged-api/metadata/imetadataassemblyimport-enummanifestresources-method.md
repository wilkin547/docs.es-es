---
title: IMetaDataAssemblyImport::EnumManifestResources (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7abcb7b69d0f0f2c53cd236c9b4092a94e0f421c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110682"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a>IMetaDataAssemblyImport::EnumManifestResources (Método)
Obtiene un puntero a un enumerador para los recursos que se hace referencia en el manifiesto del ensamblado actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Un puntero en el enumerador. Esto debe ser un valor null valor cuando el `EnumManifestResources` se llama al método por primera vez.  
  
 `rManifestResources`  
 [out] Matriz utilizada para almacenar el `mdManifestResource` los tokens de metadatos.  
  
 `cMax`  
 [in] El número máximo de `mdManifestResource` tokens que se pueden colocar en `rManifestResources`.  
  
 `pcTokens`  
 [out] El número de `mdManifestResource` tokens realmente están colocan en `rManifestResources`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumManifestResources` se devolvió correctamente.|  
|`S_FALSE`|No hay ningún token para enumerar. En este caso, `pcTokens` se establece en cero.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
