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
ms.openlocfilehash: 989e99198efd1519f607a2e3164ff4de584e88af
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679889"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a>\_AxlPublicKeyBlobToPublicKeyToken función)

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
  
## <a name="see-also"></a>Consulte también

- [Authenticode](index.md)
