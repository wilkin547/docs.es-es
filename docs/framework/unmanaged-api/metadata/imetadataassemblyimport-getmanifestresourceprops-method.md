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
ms.openlocfilehash: c0b6d53ce3be3aed6a577bf6e38a281928499848
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009033"
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
 de `mdManifestResource`Token que representa el recurso para el que se van a obtener las propiedades.  
  
 `szName`  
 enuncia Nombre del recurso.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName` .  
  
 `pchName`  
 enuncia Puntero al número de caracteres anchos realmente devueltos en `szName` .  
  
 `ptkImplementation`  
 enuncia Un puntero a un `mdFile` token o `mdAssemblyRef` token que representa el archivo o ensamblado, respectivamente, que contiene el recurso.  
  
 `pdwOffset`  
 enuncia Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.  
  
 `pdwResourceFlags`  
 enuncia Puntero a las marcas que describen los metadatos aplicados a un recurso. El valor de flags es una combinación de uno o más valores de [CorManifestResourceFlags (](cormanifestresourceflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
