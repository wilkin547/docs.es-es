---
description: 'Más información acerca de: _AxlGetIssuerPublicKeyHash función'
title: _AxlGetIssuerPublicKeyHash (Función)
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
topic_type:
- apiref
ms.openlocfilehash: 586a072b33376a2fdade119fe3db0f48addfa3f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747366"
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

 `pChainContext`\
 [in] Blob de clave pública CSP. Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

 `ppwszPublicKeyHash`\
 [out] Puntero a WCHAR * para recibir el token de clave pública de codificación hexadecimal.

## <a name="return-value"></a>Valor devuelto

 `S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.

## <a name="requirements"></a>Requisitos

**Ensamblado**: clr.dll

## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
