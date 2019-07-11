---
title: ExportNestedTypeForwarder (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb8fba433c5f7ef9701caf61971841672f46b425
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742039"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder (Método)
Agrega un reenviador de tipos para un tipo anidado a la tabla de tipos del ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
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
 Id. del ensamblado para exportar.  
  
 `FileToken`  
 Identificador de token o el ensamblado del archivo que define el tipo de archivo.  
  
 `TypeToken`  
 Símbolo (token) para el tipo.  
  
 `ParentType`  
 Token del tipo primario.  
  
 `pszTypename`  
 Nombre de tipo completo para exportar.  
  
 `dwFlags`  
 `ComType` marca como `tdPublic` o `tdNested`.  
  
 `pType`  
 Recibe el token del tipo de exportación. Esto sólo es necesario para emitir tipos anidados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
