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
ms.openlocfilehash: 2748460826deb422a3851713db11343209fe449a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449558"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a>IMetaDataAssemblyImport::EnumManifestResources (Método)
Obtiene un puntero a un enumerador para los recursos a los que se hace referencia en el manifiesto del ensamblado actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser un valor NULL cuando se llama al método `EnumManifestResources` por primera vez.  
  
 `rManifestResources`  
 enuncia Matriz usada para almacenar los tokens de metadatos de `mdManifestResource`.  
  
 `cMax`  
 de Número máximo de tokens de `mdManifestResource` que se pueden colocar en `rManifestResources`.  
  
 `pcTokens`  
 enuncia Número de tokens de `mdManifestResource` realmente colocados en `rManifestResources`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumManifestResources` devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En este caso, `pcTokens` se establece en cero.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
