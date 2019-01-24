---
title: ISymUnmanagedMethod::GetParameters (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0fc5fd29b8b423ddd3a659ee2fc8a339eea0105
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733888"
---
# <a name="isymunmanagedmethodgetparameters-method"></a>ISymUnmanagedMethod::GetParameters (Método)
Obtiene los parámetros de este método. Los parámetros se devuelven en el orden en que se definen dentro de la firma del método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cParams`  
 [in] Tamaño de la matriz `params`.  
  
 `pcParams`  
 [in] Un puntero a un `ULONG32` que recibe el tamaño del búfer que es necesario para contener los parámetros.  
  
 `params`  
 [out] Un puntero al búfer que recibe los parámetros.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
