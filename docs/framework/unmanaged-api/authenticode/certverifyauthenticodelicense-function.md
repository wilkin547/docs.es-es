---
description: 'Más información acerca de: Certverifyauthenticodelicense ((función)'
title: CertVerifyAuthenticodeLicense (Función)
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
topic_type:
- apiref
ms.openlocfilehash: 0174223a4c1b984bf2d5d957219a85230fef8d0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772853"
---
# <a name="certverifyauthenticodelicense-function"></a>CertVerifyAuthenticodeLicense (Función)

Comprueba la validez de una licencia Authenticode XrML.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CertVerifyAuthenticodeLicense (
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,
    [in]   OPTIONAL DWORD                     dwFlags,
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo
);
```

## <a name="parameters"></a>Parámetros

 `pLicenseBlob`\
 [in] Licencia Authenticode XrML que se va a comprobar.

 Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

 `dwFlags`\
 [in] Opcional. Una combinación de los siguientes valores:

- AXL_REVOCATION_NO_CHECK

- AXL_REVOCATION_CHECK_END_CERT_ONLY

- AXL_REVOCATION_CHECK_ENTIRE_CHAIN

- AXL_URL_CACHE_ONLY_RETRIEVAL

- AXL_LIFETIME_SIGNING

- AXL_TRUST_MICROSOFT_ROOT_ONLY

 `pSignerInfo`\
 [out] Para recibir la información del firmante. Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE. Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodesignerinfo (](certfreeauthenticodesignerinfo-function.md) después del uso.

 Vea [estructura de AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md).

 `pTimestamperInfo`\
 [out] Para recibir la información del autor de la marca de hora, si está disponible. Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE. Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodetimestamperinfo (](certfreeauthenticodetimestamperinfo-function.md) después del uso.

 Vea [estructura de AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md).

## <a name="return-value"></a>Valor devuelto

 Si la operación se realiza correctamente, devuelve `S_OK`. De lo contrario, devuelve un código de error.

## <a name="requirements"></a>Requisitos

**Ensamblado**: clr.dll

## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
- [Método GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
