---
title: ISymUnmanagedDispose::Destruir (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a4a0bac056c7c88a491ac05a17b662ace833df1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614463"
---
# <a name="isymunmanageddisposedestroy-method"></a>ISymUnmanagedDispose::Destruir (Método)
Hace que el objeto subyacente liberar todas las referencias internas y devuelva un error en las llamadas de método subsiguientes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedDispose (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
