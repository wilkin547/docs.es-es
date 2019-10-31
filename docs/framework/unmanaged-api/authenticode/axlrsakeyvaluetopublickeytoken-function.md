---
title: _AxlRSAKeyValueToPublicKeyToken función)
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 1f53df33a65d3f75b7574eda3507e370c2e086ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099815"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a>\_función AxlRSAKeyValueToPublicKeyToken

Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pModulusBlob`  
 de El BLOB de módulo con codificación base64 (del elemento \<módulo >).  Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `pExponentBlob`  
 de El BLOB de exponente con codificación base64 (del elemento > exponente \<). Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `ppwszPublicKeyToken`  
 [out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
