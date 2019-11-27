---
title: ISymUnmanagedDocument::GetDocumentType (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
ms.openlocfilehash: 3def5db8912bc7e27c0c76898b7bafc8eb3ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449194"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a>ISymUnmanagedDocument::GetDocumentType (Método)
Obtiene el tipo de documento de este documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pRetVal`  
 enuncia Puntero a una variable que recibe el tipo de documento.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente.  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedDocument (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
