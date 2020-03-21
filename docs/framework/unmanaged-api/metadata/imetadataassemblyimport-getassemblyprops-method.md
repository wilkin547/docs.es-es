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
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177783"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps (Método)
Obtiene el conjunto de propiedades del ensamblado con la firma de metadatos especificada.  
  
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
 [in]. El `mdAssembly` token de metadatos que representa el ensamblado para el que se obtienen las propiedades.  
  
 `ppbPublicKey`  
 [fuera] Un puntero a la clave pública o al token de metadatos.  
  
 `pcbPublicKey`  
 [fuera] El número de bytes de la clave pública devuelta.  
  
 `pulHashAlgId`  
 [fuera] Puntero al algoritmo utilizado para aplicar hash a los archivos del ensamblado.  
  
 `szName`  
 [fuera] El nombre simple del ensamblado.  
  
 `cchName`  
 [en] El tamaño, en caracteres `szName`anchos, de .  
  
 `pchName`  
 [fuera] El número de caracteres `szName`anchos realmente devueltos en .  
  
 `pMetaData`  
 [fuera] Puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.  
  
 `pdwAssemblyFlags`  
 [fuera] Indicadores que describen los metadatos aplicados a un ensamblado. Este valor es una combinación de uno o más [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
