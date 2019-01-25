---
title: ImportFileEx (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0381ee61a0128a8ae303d44198f8d391b4531a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660624"
---
# <a name="importfileex-method"></a>ImportFileEx (Método)
Importaciones indican el ensamblado o módulo sin enlazar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pszFilename`  
 Nombre completo del archivo desde el que se va a importar.  
  
 `pszTargetName`  
 Nombre opcional del archivo de destino.  
  
 `fSmartImport`  
 Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.  
  
 `dwOpenFlags`  
 Marcas que se van a pasar a [OpenScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Recibe el identificador del archivo que se va a importar.  
  
 `ppAssemblyScope`  
 Recibe el ámbito de la importación de ensamblado [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz. Se establece en NULL si el archivo no es un ensamblado.  
  
 `pdwCountOfScopes`  
 Recibe el recuento de los archivos importados de los ámbitos.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
