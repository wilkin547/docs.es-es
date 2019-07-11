---
title: ImportFile2 (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1193af7b7375dfd3367c12fdb0067c9c30c614f0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741753"
---
# <a name="importfile2-method"></a>ImportFile2 (Método)
Importa ensamblados y módulos no enlazados. Este método es similar a [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), pero funciona incluso si no existe el archivo que se importa en el disco.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `pszFilename`  
 Nombre del archivo que desea importar.  
  
 `pszTargetName`  
 Nombre de archivo de salida opcionales que puede usarse para cambiar el nombre del archivo porque está vinculado en el ensamblado.  
  
 `pAssemblyScopeIn`  
 Ámbito opcional [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz.  
  
 `fSmartImport`  
 Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.  
  
 `pImportToken`  
 Recibe el Id. del archivo o ensamblado.  
  
 `ppAssemblyScope`  
 Recibe el [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz. Es NULL si el archivo no es un ensamblado.  
  
 `pdwCountOfScopes`  
 Recibe el número de archivos y/o ámbitos importados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
