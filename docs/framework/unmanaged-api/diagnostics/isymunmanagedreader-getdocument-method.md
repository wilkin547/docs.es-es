---
title: ISymUnmanagedReader::GetDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 4604d78f66b872a30457c51bf65890caf613c4fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707638"
---
# <a name="isymunmanagedreadergetdocument-method"></a>ISymUnmanagedReader::GetDocument (Método)

Busca un documento. El idioma del documento, el proveedor y el tipo son opcionales.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  

 `url`  
 de Dirección URL que identifica el documento.  
  
 `language`  
 de Lenguaje del documento. Este parámetro es opcional.  
  
 `languageVendor`  
 de La identidad del proveedor para el idioma del documento. Este parámetro es opcional.  
  
 `documentType`  
 de Tipo del documento. Este parámetro es opcional.  
  
 `pRetVal`  
 enuncia Puntero a la interfaz devuelta.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)
