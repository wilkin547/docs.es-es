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
ms.openlocfilehash: 0ae4ddd07a2a3d3ab9b5d024eceb43329db96915
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787508"
---
# <a name="exporttypeforwarder-method"></a>ExportTypeForwarder (Método)
Agrega un reenviador de tipos a la tabla de tipos del ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `tkAssemblyRef`  
 Referencia al ensamblado al que hace referencia el reenviador de tipos.  
  
 `pszTypename`  
 Nombre completo del tipo que se va a exportar.  
  
 `dwFlags`  
 `ComType`marcas como `tdPublic` o `tdNested`. Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Recibe el token del tipo exportado. Esto solo es necesario para emitir tipos anidados.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
