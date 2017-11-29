---
title: "ISymUnmanagedWriter2::DefineLocalVariable2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineLocalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 595cc3d8c503a5a6b2cbcb6665f7ff8aff5044d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2 (Método)
Define una única variable en el ámbito léxico actual. Este método puede llamarse varias veces para una variable del mismo nombre que tenga varias ubicaciones en un ámbito. En este caso, sin embargo, los valores de la `startOffset` y `endOffset` no deben solaparse con parámetros.  
  
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
  
#### <a name="parameters"></a>Parámetros  
 `name`  
 [in] El nombre de variable local.  
  
 `attributes`  
 [in] Atributos de la variable locales.  
  
 `sigToken`  
 [in] El token de metadatos de la firma.  
  
 `addrKind`  
 [in] El tipo de dirección.  
  
 `addr1`  
 [in] La primera dirección para la especificación de parámetros.  
  
 `addr2`  
 [in] La segunda dirección para la especificación de parámetros.  
  
 `addr3`  
 [in] La tercera dirección de la especificación de parámetros.  
  
 `startOffset`  
 [in] Desplazamiento inicial de la variable. Este parámetro es opcional. Si es 0, se omite este parámetro y la variable se define en todo el ámbito. Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.  
  
 `endOffset`  
 [in] Desplazamiento final de la variable. Este parámetro es opcional. Si es 0, se omite este parámetro y la variable se define en todo el ámbito. Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedWriter2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [DefineLocalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
