---
title: _AxlGetIssuerPublicKeyHash (Función)
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b101a912eb58ed14f81d847ea2fd6ce9f22c065
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787092"
---
# <a name="_axlgetissuerpublickeyhash-function"></a>\_AxlGetIssuerPublicKeyHash función)
Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pChainContext`  
 [in] Blob de clave pública CSP. Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `ppwszPublicKeyHash`  
 [out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.  
  
## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
