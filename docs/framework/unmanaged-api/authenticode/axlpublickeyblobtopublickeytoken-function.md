---
description: 'Más información acerca de: _AxlPublicKeyBlobToPublicKeyToken función'
title: _AxlPublicKeyBlobToPublicKeyToken (Función)
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
topic_type:
- apiref
ms.openlocfilehash: df0b484bad64051eb892d4898a6c90777cc2d5cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781940"
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

 `pCspPublicKeyBlob`\
 [in] Blob de clave pública CSP.

 `ppwszPublicKeyHash`\
 [out] Puntero a WCHAR * para recibir el hash de clave pública de codificación hexadecimal.

## <a name="return-value"></a>Valor devuelto

 `S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.

## <a name="requirements"></a>Requisitos

**Ensamblado**: clr.dll

## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
