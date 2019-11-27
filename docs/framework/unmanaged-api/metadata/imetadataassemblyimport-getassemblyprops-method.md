---
title: IMetaDataAssemblyImport::GetAssemblyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449434"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps (Método)
Obtiene el conjunto de propiedades para el ensamblado con la firma de metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  
 `mda`  
 [in]. Símbolo (token) de metadatos de `mdAssembly` que representa el ensamblado para el que se van a obtener las propiedades.  
  
 `ppbPublicKey`  
 enuncia Puntero a la clave pública o al token de metadatos.  
  
 `pcbPublicKey`  
 enuncia Número de bytes de la clave pública devuelta.  
  
 `pulHashAlgId`  
 enuncia Puntero al algoritmo utilizado para aplicar un algoritmo hash a los archivos del ensamblado.  
  
 `szName`  
 enuncia Nombre simple del ensamblado.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 enuncia Número de caracteres anchos realmente devueltos en `szName`.  
  
 `pMetaData`  
 enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.  
  
 `pdwAssemblyFlags`  
 enuncia Marcas que describen los metadatos aplicados a un ensamblado. Este valor es una combinación de uno o más valores de [corassemblyflags (](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
