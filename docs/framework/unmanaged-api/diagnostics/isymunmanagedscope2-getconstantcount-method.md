---
title: ISymUnmanagedScope2::GetConstantCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2752cf7dcdf0a33e5b6f4e7a51f3d63476c40e4f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777936"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a>ISymUnmanagedScope2::GetConstantCount (Método)
Obtiene un recuento de las constantes definidas en este ámbito.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pRetVal`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedScope2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
