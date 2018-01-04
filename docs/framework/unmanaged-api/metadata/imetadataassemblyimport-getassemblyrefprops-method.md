---
title: "IMetaDataAssemblyImport::GetAssemblyRefProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76ae1d81db314530ab33a42cb99824da1745dff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps (Método)
Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `mdar`  
 [in] El `mdAssemblyRef` símbolo (token) de metadatos que representa la referencia de ensamblado para el que se va a obtener las propiedades.  
  
 `ppbPublicKeyOrToken`  
 [out] Un puntero a la clave pública o el token de metadatos.  
  
 `pcbPublicKeyOrToken`  
 [out] El número de bytes de la clave pública devuelta o símbolo (token).  
  
 `szName`  
 [out] El nombre simple del ensamblado.  
  
 `cchName`  
 [in] El tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 [out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.  
  
 `pMetaData`  
 [out] Un puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.  
  
 `ppbHashValue`  
 [out] Un puntero con el valor hash. Este es el valor hash, utilizando el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado al que hace referencia, a menos que marca el arfFullOriginator de la [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) se establece la enumeración.  
  
 `pcbHashValue`  
 [out] El número de caracteres anchos en el valor hash devuelto.  
  
 `pdwAssemblyRefFlags`  
 [out] Un puntero a marcas que describen los metadatos aplicados a un ensamblado. El valor de flags es una combinación de uno o varios [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve S_OK si se realiza correctamente; en caso contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror.h.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
