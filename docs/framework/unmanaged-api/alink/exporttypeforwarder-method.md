---
title: ExportTypeForwarder (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03949fb52d23e3b0f107f9f1d5208208369c3960
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574620"
---
# <a name="exporttypeforwarder-method"></a>ExportTypeForwarder (Método)
Agrega un reenviador de tipos a la tabla de tipos del ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tkAssemblyRef`  
 Referencia al ensamblado al que hace referencia el reenviador de tipos.  
  
 `pszTypename`  
 Nombre de tipo completo para exportar.  
  
 `dwFlags`  
 `ComType` marca como `tdPublic` o `tdNested`. Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Recibe el token del tipo exportado. Esto sólo es necesario para emitir tipos anidados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también
- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
