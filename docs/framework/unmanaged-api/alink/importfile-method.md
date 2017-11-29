---
title: "ImportFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportFile
api_location: alink.dll
api_type: COM
f1_keywords: ImportFile
helpviewer_keywords: ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 46830699ba43c406da313653e1910e8f7a18a2ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="importfile-method"></a>ImportFile (Método)
Importa ensamblados y módulos no enlazados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pszFilename`  
 Nombre completo del archivo que desea importar.  
  
 `pszTargetName`  
 Nombre de archivo de salida opcionales que puede usarse para cambiar el nombre del archivo cuando se vincule al ensamblado.  
  
 `fSmartImport`  
 Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.  
  
 `pImportToken`  
 Puntero al símbolo (token) donde se almacenará un identificador de archivo único. El archivo puede ser un ensamblado o un archivo.  
  
 `ppAssemblyScope`  
 Recibe el puntero a [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). Puede ser NULL si el archivo no es un ensamblado.  
  
 `pdwCountOfScopes`  
 Puntero al recuento de archivos y/o ámbitos que se han importado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
