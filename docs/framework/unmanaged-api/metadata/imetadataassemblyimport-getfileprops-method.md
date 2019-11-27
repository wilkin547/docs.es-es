---
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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447214"
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
 de Símbolo (token) de metadatos de `mdFile` que representa el archivo para el que se van a obtener las propiedades.  
  
 `szName`  
 enuncia Nombre simple del archivo.  
  
 `cchName`  
 de Tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 enuncia Número de caracteres anchos realmente devueltos en `szName`.  
  
 `ppbHashValue`  
 enuncia Puntero al valor hash. Este es el hash, mediante el algoritmo SHA-1, del archivo.  
  
 `pcbHashValue`  
 enuncia Número de caracteres anchos en el valor hash devuelto.  
  
 `pdwFileFlags`  
 enuncia Puntero a las marcas que describen los metadatos aplicados a un archivo. El valor de flags es una combinación de uno o más valores de [CorFileFlags (](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
