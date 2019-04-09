---
title: IMetaDataAssemblyEmit::SetManifestResourceProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6fbc3f41e95730e93bd907762dd8cd4205037c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187309"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>IMetaDataAssemblyEmit::SetManifestResourceProps (Método)
Modifica la estructura de metadatos `ManifestResource` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mr`  
 [in] El símbolo (token) que especifica el `ManifestResource` estructura de metadatos que se puede modificar.  
  
 `tkImplementation`  
 [in] El token de tipo `File` o `AssemblyRef`, que se asigna al proveedor de recursos.  
  
 `dwOffset`  
 [in] El desplazamiento al principio del recurso dentro del archivo.  
  
 `dwResourceFlags`  
 [in] Una combinación bit a bit de valores de indicador que especifican los atributos del recurso.  
  
## <a name="remarks"></a>Comentarios  
 Para crear un `ManifestResource` estructura de los metadatos, use el [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
