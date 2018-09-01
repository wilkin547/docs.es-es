---
title: _AxlRSAKeyValueToPublicKeyToken (función)
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e09391af9b5d71cfa423b3bf1a2b307117d0dee1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385892"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a>\_Función AxlRSAKeyValueToPublicKeyToken

Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a>Parámetros  
 `pModulusBlob`  
 [in] El blob Modulus con codificación base64 (desde el \<Modulus > elemento).  Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.  
  
 `pExponentBlob`  
 [in] El blob Exponent con codificación base64 (desde el \<exponente > elemento). Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.  
  
 `ppwszPublicKeyToken`  
 [out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
