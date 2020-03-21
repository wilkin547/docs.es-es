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
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175972"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps (Método)
Obtiene el conjunto de propiedades de la referencia de ensamblado con la firma de metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 [en] El `mdAssemblyRef` token de metadatos que representa la referencia de ensamblado para la que se obtienen las propiedades.  
  
 `ppbPublicKeyOrToken`  
 [fuera] Un puntero a la clave pública o al token de metadatos.  
  
 `pcbPublicKeyOrToken`  
 [fuera] El número de bytes de la clave pública o token devuelto.  
  
 `szName`  
 [fuera] El nombre simple del ensamblado.  
  
 `cchName`  
 [en] El tamaño, en caracteres `szName`anchos, de .  
  
 `pchName`  
 [fuera] Un puntero al número de caracteres `szName`anchos realmente devueltos en .  
  
 `pMetaData`  
 [fuera] Puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.  
  
 `ppbHashValue`  
 [fuera] Un puntero al valor hash. Este es el hash, mediante el algoritmo `PublicKey` SHA-1, de la propiedad del ensamblado al que se hace referencia, a menos que se establezca la marca arfFullOriginator de la enumeración [AssemblyRefFlags.](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)  
  
 `pcbHashValue`  
 [fuera] El número de caracteres anchos en el valor hash devuelto.  
  
 `pdwAssemblyRefFlags`  
 [fuera] Puntero a marcas que describen los metadatos aplicados a un ensamblado. El valor flags es una combinación de uno o varios [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve S_OK si se realiza correctamente; de lo contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror.h.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
