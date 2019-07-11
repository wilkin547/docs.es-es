---
title: ISymUnmanagedWriter::DefineLocalVariable (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9466df3f6413f86eb8558f0037b96c254b2a2e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777342"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>ISymUnmanagedWriter::DefineLocalVariable (Método)
Define una única variable en el ámbito léxico actual. Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito. En este caso, sin embargo, los valores de la `startOffset` y `endOffset` parámetros no deben superponerse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 [in] Un puntero a un `WCHAR` que define el nombre de variable local.  
  
 `attributes`  
 [in] Atributos de la variable locales.  
  
 `cSig`  
 [in] Un `ULONG32` que indica el tamaño, en bytes, de la `signature` búfer.  
  
 `signature`  
 [in] La firma de variable local.  
  
 `addrKind`  
 [in] El tipo de dirección.  
  
 `addr1`  
 [in] La primera dirección de la especificación de parámetro.  
  
 `addr2`  
 [in] La segunda dirección de la especificación de parámetro.  
  
 `addr3`  
 [in] Tercera dirección de la especificación de parámetro.  
  
 `startOffset`  
 [in] El desplazamiento inicial de la variable. Este parámetro es opcional. Si es 0, se omite este parámetro y la variable se define en todo el ámbito. Si es un valor distinto de cero, la variable está comprendida dentro de los desplazamientos del ámbito actual.  
  
 `endOffset`  
 [in] Desplazamiento final de la variable. Este parámetro es opcional. Si es 0, se omite este parámetro y la variable se define en todo el ámbito. Si es un valor distinto de cero, la variable está comprendida dentro de los desplazamientos del ámbito actual.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [DefineGlobalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [DefineLocalVariable2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
