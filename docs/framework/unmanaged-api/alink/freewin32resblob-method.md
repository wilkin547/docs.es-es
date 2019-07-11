---
title: FreeWin32ResBlob (Método)
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75aec187452e2f9f442a5d4856fe6777c03f34c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741986"
---
# <a name="freewin32resblob-method"></a>FreeWin32ResBlob (Método)
Libera el objeto binario de recursos Win32 y recursos asociados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppResBlob`  
 El objeto binario de recursos para publicarse. Este método asigna el puntero de blob a NULL.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
