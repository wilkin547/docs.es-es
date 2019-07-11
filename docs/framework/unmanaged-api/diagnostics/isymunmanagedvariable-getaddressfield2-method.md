---
title: ISymUnmanagedVariable::GetAddressField2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 463416165d2dbd7724d5cf0d29e40d8243ade34b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778321"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a>ISymUnmanagedVariable::GetAddressField2 (Método)
Obtiene el segundo campo de dirección de esta variable. Su significado depende del tipo de dirección.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pRetVal`  
 [out] Un puntero a un `ULONG32` que recibe el segundo campo de dirección.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedVariable (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [GetAddressField1 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [GetAddressField3 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [GetAddressKind (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
