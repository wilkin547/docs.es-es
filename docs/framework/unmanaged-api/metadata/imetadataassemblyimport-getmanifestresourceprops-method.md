---
title: "IMetaDataAssemblyImport::GetManifestResourceProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetManifestResourceProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29458b0b7afa5a0c0be908915b4fc91c85d28c72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps (Método)
Obtiene el conjunto de propiedades del recurso del manifiesto con la firma de metadatos especificados.  
  
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
  
#### <a name="parameters"></a>Parámetros  
 `mdmr`  
 [in] Un `mdManifestResource` símbolo (token) que representa el recurso para el que se va a obtener las propiedades.  
  
 `szName`  
 [out] El nombre del recurso.  
  
 `cchName`  
 [in] El tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 [out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.  
  
 `ptkImplementation`  
 [out] Un puntero a un `mdFile` símbolo (token) o un `mdAssemblyRef` símbolo (token) que representa el archivo o ensamblado, respectivamente, que contiene el recurso.  
  
 `pdwOffset`  
 [out] Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.  
  
 `pdwResourceFlags`  
 [out] Un puntero a marcas que describen los metadatos aplicados a un recurso. El valor de flags es una combinación de uno o varios [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
