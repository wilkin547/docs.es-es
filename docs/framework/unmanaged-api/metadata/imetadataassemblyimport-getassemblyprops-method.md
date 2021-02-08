---
description: 'Más información sobre: IMetaDataAssemblyImport:: Getassemblyprops ((método)'
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
ms.openlocfilehash: 9cd3674dcd640bce27ae5d399d0f7de0c2eeca48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784150"
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
 [in]. `mdAssembly`Token de metadatos que representa el ensamblado para el que se van a obtener las propiedades.  
  
 `ppbPublicKey`  
 enuncia Puntero a la clave pública o al token de metadatos.  
  
 `pcbPublicKey`  
 enuncia Número de bytes de la clave pública devuelta.  
  
 `pulHashAlgId`  
 enuncia Puntero al algoritmo utilizado para aplicar un algoritmo hash a los archivos del ensamblado.  
  
 `szName`  
 enuncia Nombre simple del ensamblado.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName` .  
  
 `pchName`  
 enuncia Número de caracteres anchos realmente devueltos en `szName` .  
  
 `pMetaData`  
 enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.  
  
 `pdwAssemblyFlags`  
 enuncia Marcas que describen los metadatos aplicados a un ensamblado. Este valor es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
