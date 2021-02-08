---
description: 'Más información sobre: IMetaDataAssemblyImport:: GetFileProps ((método)'
title: IMetaDataAssemblyImport::GetFileProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 6814fee7edf5478a1ce2cf2b81d8f16fa62cd3f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784111"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps (Método)

Obtiene las propiedades del archivo con la firma de metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mdf`  
 de `mdFile` Token de metadatos que representa el archivo para el que se van a obtener las propiedades.  
  
 `szName`  
 enuncia Nombre simple del archivo.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName` .  
  
 `pchName`  
 enuncia Número de caracteres anchos realmente devueltos en `szName` .  
  
 `ppbHashValue`  
 enuncia Puntero al valor hash. Este es el hash, mediante el algoritmo SHA-1, del archivo.  
  
 `pcbHashValue`  
 enuncia Número de caracteres anchos en el valor hash devuelto.  
  
 `pdwFileFlags`  
 enuncia Puntero a las marcas que describen los metadatos aplicados a un archivo. El valor de flags es una combinación de uno o más valores de [CorFileFlags (](corfileflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
