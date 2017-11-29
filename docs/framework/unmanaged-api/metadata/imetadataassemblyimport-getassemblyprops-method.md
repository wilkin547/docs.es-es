---
title: "IMetaDataAssemblyImport::GetAssemblyProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3ff9c66d483392823a1cc95163e4d5e7e81a364
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps (Método)
Obtiene el conjunto de propiedades para el ensamblado con la firma de metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `mda`  
 [in]. El `mdAssembly` símbolo (token) de metadatos que representa el ensamblado para el que se va a obtener las propiedades.  
  
 `ppbPublicKey`  
 [out] Un puntero a la clave pública o el token de metadatos.  
  
 `pcbPublicKey`  
 [out] El número de bytes de la clave pública devuelta.  
  
 `pulHashAlgId`  
 [out] Un puntero al algoritmo utilizado para resumir los archivos en el ensamblado.  
  
 `szName`  
 [out] El nombre simple del ensamblado.  
  
 `cchName`  
 [in] El tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 [out] El número de caracteres anchos realmente devueltos en `szName`.  
  
 `pMetaData`  
 [out] Un puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.  
  
 `pdwAssemblyFlags`  
 [out] Marcas que describen los metadatos aplicados a un ensamblado. Este valor es una combinación de uno o varios [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
