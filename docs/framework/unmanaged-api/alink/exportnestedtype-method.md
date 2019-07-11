---
title: ExportNestedType (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfaedad48291ac09f6959bc7b314ae0d9da76e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742041"
---
# <a name="exportnestedtype-method"></a>ExportNestedType (Método)
Especifica los tipos anidados como exportable. El [ExportType (método)](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) también puede exportar anidada tipos, pero este método es más rápido.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador del ensamblado para exportar.  
  
 `FileToken`  
 Símbolo (token) de archivo o ensamblado del archivo que define el tipo que se realicen exportable.  
  
 `TypeToken`  
 Tipo de token del tipo que se realicen exportable.  
  
 `ParentType`  
 Token del tipo primario.  
  
 `pszTypename`  
 Nombre de tipo completo para exportar.  
  
 `dwFlags`  
 `ComType` marca como `tdPublic` o `tdNested`. Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Recibe el token para el tipo exportado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
