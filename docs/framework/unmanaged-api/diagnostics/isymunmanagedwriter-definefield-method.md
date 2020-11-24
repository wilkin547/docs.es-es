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
ms.openlocfilehash: 5683c10938873821cbe998dbf13937a6a7d24d7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675092"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>ISymUnmanagedWriter::DefineField (Método)

Define una única variable que no está dentro de un método. Este método se usa para determinados campos de clases, campos de bits, etc.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de El tipo de metadatos o el token del método.  
  
 `name`  
 de Nombre del campo.  
  
 `attributes`  
 de Atributos del campo.  
  
 `cSig`  
 de `ULONG32` Que es el tamaño, en caracteres, del búfer necesario para contener la firma del campo.  
  
 `signature`  
 de Matriz de firmas de campo.  
  
 `addrKind`  
 de Tipo de dirección.  
  
 `addr1`  
 de Primera dirección de la especificación de campo.  
  
 `addr2`  
 de Segunda dirección de la especificación de campo.  
  
 `addr3`  
 de Tercera dirección de la especificación de campo.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
