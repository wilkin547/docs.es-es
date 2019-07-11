---
title: ISymUnmanagedMethod::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bb9a444d8e8b674d1f173214d8bac427f24e408
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759395"
---
# <a name="isymunmanagedmethodgettoken-method"></a>ISymUnmanagedMethod::GetToken (Método)
Devuelve el token de metadatos para este método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pToken`  
 [out] Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
