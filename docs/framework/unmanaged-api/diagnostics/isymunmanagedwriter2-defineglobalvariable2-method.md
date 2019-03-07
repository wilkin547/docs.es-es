---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 067be401b793c227d8b5caa2706f84a59d3a09df
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499048"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)
Define una única variable global.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 [in] El nombre de variable global.  
  
 `attributes`  
 [in] Atributos de la variable globales.  
  
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
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedWriter2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [DefineGlobalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
