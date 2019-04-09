---
title: IMetaDataAssemblyImport::GetAssemblyRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6c550ff7af2dda8bc06afd771024fe290339904
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089788"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps (Método)
Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificado.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `mdar`  
 [in] El `mdAssemblyRef` token de metadatos que representa la referencia de ensamblado para el que se va a obtener las propiedades.  
  
 `ppbPublicKeyOrToken`  
 [out] Un puntero a la clave pública o el token de metadatos.  
  
 `pcbPublicKeyOrToken`  
 [out] El número de bytes de la clave pública devuelta o token.  
  
 `szName`  
 [out] El nombre sencillo del ensamblado.  
  
 `cchName`  
 [in] El tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 [out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.  
  
 `pMetaData`  
 [out] Un puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.  
  
 `ppbHashValue`  
 [out] Un puntero con el valor hash. Este es el valor de hash, utilizando el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado que se hace referencia a menos que marca el arfFullOriginator de la [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) se establece la enumeración.  
  
 `pcbHashValue`  
 [out] El número de caracteres anchos en el valor hash devuelto.  
  
 `pdwAssemblyRefFlags`  
 [out] Un puntero a las marcas que describen los metadatos aplicados a un ensamblado. El valor de marcas es una combinación de uno o varios [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve S_OK si se realiza correctamente; en caso contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror.h.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
