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
ms.openlocfilehash: f6b5e12df60663b75e10b04eaa008a75d720d753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434430"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>IMetaDataAssemblyEmit::SetManifestResourceProps (Método)
Modifica la estructura de metadatos `ManifestResource` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mr`  
 de El token que especifica la estructura de metadatos de `ManifestResource` que se va a modificar.  
  
 `tkImplementation`  
 de El token, de tipo `File` o `AssemblyRef`, que se asigna al proveedor de recursos.  
  
 `dwOffset`  
 de Desplazamiento al principio del recurso dentro del archivo.  
  
 `dwResourceFlags`  
 de Combinación bit a bit de valores de marca que especifican los atributos del recurso.  
  
## <a name="remarks"></a>Comentarios  
 Para crear una estructura de metadatos de `ManifestResource`, use el método [IMetaDataAssemblyEmit::D efinemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
