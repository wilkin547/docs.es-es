---
title: _AxlPublicKeyBlobToPublicKeyToken (Función)
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
ms.openlocfilehash: 33b8f47813a3bf43bd69741c9febb150fa3a92e3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099906"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a>\_función AxlPublicKeyBlobToPublicKeyToken
Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCspPublicKeyBlob`  
 [in] Blob de clave pública CSP.  
  
 `ppwszPublicKeyHash`  
 [out] Puntero a WCHAR * para recibir el hash de clave pública de codificación hexadecimal.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.  
  
## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
