---
title: AddImport Method1
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fefc0240f6496a3e7bfb491e27a57e98cfea1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="addimport-method1"></a>AddImport Method1
Agrega las importaciones al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador único del ensamblado que se va a aumentar.  
  
 `ImportToken`  
 Identificador único, se recupera de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del archivo que desea importar.  
  
 `dwFlags`  
 COM + FileDef se marca como `ffContainsNoMetaData` y `ffWriteable`. `dwFlags` se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Puntero al token que recibe el identificador para el archivo resultante.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
