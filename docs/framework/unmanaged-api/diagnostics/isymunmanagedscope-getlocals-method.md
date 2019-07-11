---
title: ISymUnmanagedScope::GetLocals (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e45f5411d48032b86403e35358d7ce83d5f97c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777915"
---
# <a name="isymunmanagedscopegetlocals-method"></a>ISymUnmanagedScope::GetLocals (Método)
Obtiene las variables locales definidas en este ámbito.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cLocals`  
 [in] Un `ULONG32` que indica el tamaño de la `locals` matriz.  
  
 `pcLocals`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables locales.  
  
 `locals`  
 [out] Matriz que recibe las variables locales.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedScope (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
