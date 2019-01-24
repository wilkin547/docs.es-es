---
title: ISymUnmanagedScope::GetChildren (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f9bd6ae34903798a29f8666dfdba3e102fae28db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584563"
---
# <a name="isymunmanagedscopegetchildren-method"></a>ISymUnmanagedScope::GetChildren (Método)
Obtiene a los elementos secundarios de este ámbito.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cChildren`  
 [in] Un `ULONG32` que indica el tamaño de la `children` matriz.  
  
 `pcChildren`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los elementos secundarios.  
  
 `children`  
 [out] La matriz devuelta de los elementos secundarios.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedScope (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [GetParent (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
