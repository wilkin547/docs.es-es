---
title: ISymUnmanagedWriter::DefineDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1c214918b4a41ac989a3804c9146c4a54c5909f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738214"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>ISymUnmanagedWriter::DefineDocument (Método)
Define un documento de origen. Se proporcionan los GUID para lenguajes conocidos, proveedores y tipos de documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `url`  
 [in] Un puntero a un `WCHAR` que define el localizador uniforme de recursos (URL) que identifica el documento.  
  
 `language`  
 [in] Un puntero a un GUID que define el lenguaje del documento.  
  
 `languageVendor`  
 [in] Un puntero a un GUID que define la identidad del proveedor para el lenguaje del documento.  
  
 `documentType`  
 [in] Un puntero a un GUID que define el tipo del documento.  
  
 `pRetVal`  
 [out] Un puntero a la devuelta [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaz.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
