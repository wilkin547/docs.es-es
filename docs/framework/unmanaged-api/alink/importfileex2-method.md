---
title: ImportFileEx2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be6332c76b3dae9c02e1a939286b70438ee14cfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400684"
---
# <a name="importfileex2-method"></a>ImportFileEx2 (Método)
Importa ensamblados y módulos no enlazados. Este método es similar a [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pszFilename`  
 Nombre del archivo que desea importar.  
  
 `pszTargetName`  
 Nombre opcional del archivo de destino.  
  
 `pAssemblyScopeIn`  
 Ámbito de importación opcional [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz.  
  
 `fSmartImport`  
 Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.  
  
 `dwOpenFlags`  
 Marcas que se van a pasar a [OpenScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Recibe el identificador único para el ensamblado o el archivo.  
  
 `ppAssemblyScope`  
 Recibe el ámbito de la importación de ensamblado [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz. Puede ser NULL si el archivo no es un ensamblado.  
  
 `pdwCountOfScopes`  
 Recibe el número de archivos y/o ámbitos importados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
