---
title: IMetaDataAssemblyImport::GetManifestResourceProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436321"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps (Método)
Obtiene el conjunto de propiedades del recurso de manifiesto con la firma de metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mdmr`  
 de `mdManifestResource` token que representa el recurso para el que se van a obtener las propiedades.  
  
 `szName`  
 enuncia Nombre del recurso.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 enuncia Puntero al número de caracteres anchos que se devuelven realmente en `szName`.  
  
 `ptkImplementation`  
 enuncia Un puntero a un token de `mdFile` o un token de `mdAssemblyRef` que representa el archivo o ensamblado, respectivamente, que contiene el recurso.  
  
 `pdwOffset`  
 enuncia Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.  
  
 `pdwResourceFlags`  
 enuncia Puntero a las marcas que describen los metadatos aplicados a un recurso. El valor de flags es una combinación de uno o más valores de [CorManifestResourceFlags (](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
