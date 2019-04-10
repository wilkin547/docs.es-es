---
title: ExportType (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95ff27143453e7772b4a463fa66ca039bbb715fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226922"
---
# <a name="exporttype-method"></a>ExportType (Método)
Especifica que un tipo es exportable.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Id. del ensamblado para exportar.  
  
 `FileToken`  
 Archivo de token o identificador de ensamblado del archivo que define el tipo exportable.  
  
 `TypeToken`  
 Token del tipo que se realicen exportable.  
  
 `pszTypename`  
 Nombre de tipo completo que se realicen exportable.  
  
 `dwFlags`  
 `ComType` marca como `tdPublic` o `tdNested`. Este parámetro puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Recibe el token para el tipo exportado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (Interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
