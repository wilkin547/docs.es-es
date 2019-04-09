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
ms.openlocfilehash: 49476a4417e5431842f8e2ba0371c53c5c9f03e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207830"
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
  
## <a name="parameters"></a>Parámetros  
 `pModulusBlob`  
 [in] El blob Modulus con codificación base64 (desde el \<Modulus > elemento).  Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.  
  
 `pExponentBlob`  
 [in] El blob Exponent con codificación base64 (desde el \<exponente > elemento). Consulte la [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) estructura.  
  
 `ppwszPublicKeyToken`  
 [out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
