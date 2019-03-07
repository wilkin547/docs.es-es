---
title: ISymUnmanagedWriter::DefineField (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a385e42ae3a494f6d2196e21b552c6b5679dda9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468889"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>ISymUnmanagedWriter::DefineField (Método)
Define una única variable que no está dentro de un método. Este método es usados para ciertos campos en clases, campos de bits y así sucesivamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parámetros  
 `parent`  
 [in] El tipo de metadatos o el método token.  
  
 `name`  
 [in] El nombre del campo.  
  
 `attributes`  
 [in] Los atributos del campo.  
  
 `cSig`  
 [in] Un `ULONG32` que es el tamaño, en caracteres, del búfer necesario para contener la firma del campo.  
  
 `signature`  
 [in] Matriz de firmas de campo.  
  
 `addrKind`  
 [in] El tipo de dirección.  
  
 `addr1`  
 [in] La primera dirección de la especificación de campo.  
  
 `addr2`  
 [in] La segunda dirección de la especificación de campo.  
  
 `addr3`  
 [in] Tercera dirección de la especificación de campo.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
