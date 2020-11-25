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
ms.openlocfilehash: 25aefff46f7557f89f27d1eccab58c9c70d2d13e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722120"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps (Método)

Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificada.  
  
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
 de `mdAssemblyRef` Símbolo (token) de metadatos que representa la referencia del ensamblado para el que se van a obtener las propiedades.  
  
 `ppbPublicKeyOrToken`  
 enuncia Puntero a la clave pública o al token de metadatos.  
  
 `pcbPublicKeyOrToken`  
 enuncia Número de bytes de la clave pública o el token devueltos.  
  
 `szName`  
 enuncia Nombre simple del ensamblado.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName` .  
  
 `pchName`  
 enuncia Puntero al número de caracteres anchos realmente devueltos en `szName` .  
  
 `pMetaData`  
 enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.  
  
 `ppbHashValue`  
 enuncia Puntero al valor hash. Este es el hash, mediante el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado al que se hace referencia, a menos que se establezca la marca arfFullOriginator de la enumeración [AssemblyRefFlags (](assemblyrefflags-enumeration.md) .  
  
 `pcbHashValue`  
 enuncia Número de caracteres anchos en el valor hash devuelto.  
  
 `pdwAssemblyRefFlags`  
 enuncia Puntero a las marcas que describen los metadatos aplicados a un ensamblado. El valor de flags es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve S_OK si se realiza correctamente; de lo contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror. h.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
