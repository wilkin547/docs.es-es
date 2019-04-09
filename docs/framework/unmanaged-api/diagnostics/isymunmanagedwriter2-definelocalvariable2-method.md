---
title: ISymUnmanagedWriter2::DefineLocalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2caa9b48fc92a1b2e82f574d37d99758e19382c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133203"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2 (Método)
Define una única variable en el ámbito léxico actual. Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito. En este caso, sin embargo, los valores de la `startOffset` y `endOffset` parámetros no deben superponerse.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 [in] El nombre de variable local.  
  
 `attributes`  
 [in] Atributos de la variable locales.  
  
 `sigToken`  
 [in] El token de metadatos de la firma.  
  
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
 **Encabezado**: CorSym.idl  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter2 (Interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [Método DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
