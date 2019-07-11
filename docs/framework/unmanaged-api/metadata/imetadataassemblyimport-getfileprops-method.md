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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f3883b0cd1b7aca6265b738eace483c81eb37b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760142"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps (Método)
Obtiene las propiedades del archivo con la firma de metadatos especificado.  
  
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
 [in] El `mdFile` token de metadatos que representa el archivo que se va a obtener las propiedades.  
  
 `szName`  
 [out] El nombre sencillo del archivo.  
  
 `cchName`  
 [in] El tamaño, en caracteres anchos, de `szName`.  
  
 `pchName`  
 [out] El número de caracteres anchos realmente devueltos en `szName`.  
  
 `ppbHashValue`  
 [out] Un puntero con el valor hash. Este es el hash, utilizando el algoritmo SHA-1, del archivo.  
  
 `pcbHashValue`  
 [out] El número de caracteres anchos en el valor hash devuelto.  
  
 `pdwFileFlags`  
 [out] Un puntero a los marcadores que describen los metadatos aplicados a un archivo. El valor de marcas es una combinación de uno o varios [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
