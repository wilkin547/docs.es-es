---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineDocument'
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
ms.openlocfilehash: 35e918292e6ee50e17932645e003d19513e2397a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762544"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>ISymUnmanagedWriter::DefineDocument (Método)

Define un documento de origen. Se proporcionan GUID para los lenguajes, proveedores y tipos de documento conocidos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  

 `url`  
 de Un puntero a `WCHAR` que define el localizador uniforme de recursos (URL) que identifica el documento.  
  
 `language`  
 de Un puntero a un GUID que define el idioma del documento.  
  
 `languageVendor`  
 de Un puntero a un GUID que define la identidad del proveedor para el idioma del documento.  
  
 `documentType`  
 de Un puntero a un GUID que define el tipo del documento.  
  
 `pRetVal`  
 enuncia Puntero a la interfaz [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) devuelta.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
