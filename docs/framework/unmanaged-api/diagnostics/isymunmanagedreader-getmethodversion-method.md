---
title: ISymUnmanagedReader::GetMethodVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5d4145e6c76cf95f2468a3f5ad59edcd310423e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160880"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a>ISymUnmanagedReader::GetMethodVersion (Método)
Obtiene la versión del método. La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método. Recompilación puede realizarse sin cambios en el método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pMethod`  
 [in] El método que se va a obtener la versión.  
  
 `version`  
 [out] Un puntero a una variable que recibe la versión del método.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
