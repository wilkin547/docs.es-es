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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8786005921d671d873151a4f2e2f5a38d6df21c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501467"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps (Método)
Obtiene el conjunto de propiedades del recurso del manifiesto con la firma de metadatos especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in] Un `mdManifestResource` token que representa el recurso para el que se va a obtener las propiedades.  
  
 `szName`  
 [out] El nombre del recurso.  
  
 `cchName`  
 [in] El tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 [out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.  
  
 `ptkImplementation`  
 [out] Un puntero a un `mdFile` token o un `mdAssemblyRef` token que representa el archivo o ensamblado, respectivamente, que contiene el recurso.  
  
 `pdwOffset`  
 [out] Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.  
  
 `pdwResourceFlags`  
 [out] Un puntero a las marcas que describen los metadatos aplicados a un recurso. El valor de marcas es una combinación de uno o varios [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
