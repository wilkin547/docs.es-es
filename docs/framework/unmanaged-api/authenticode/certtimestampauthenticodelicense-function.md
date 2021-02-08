---
description: 'Más información acerca de: Certtimestampauthenticodelicense ((función)'
title: CertTimestampAuthenticodeLicense (Función)
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
topic_type:
- apiref
ms.openlocfilehash: 79b1a924a99a76c18e6434abfed0a90da71eb6f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772924"
---
# <a name="certtimestampauthenticodelicense-function"></a>CertTimestampAuthenticodeLicense (Función)

Aplica marcas de hora a una licencia Authenticode XrML.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CertTimestampAuthenticodeLicense (
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,
    [in]  LPCWSTR            pwszTimestampURI,
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob
);
```

## <a name="parameters"></a>Parámetros

 `pSignedLicenseBlob`\
 [in] Licencia Authenticode XrML firmada a la que se va a aplicar la marca de hora. Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

 `pwszTimestampURI`\
 [in] URI del servidor de marca de hora.

 `pTimestampSignatureBlob`\
 [out] Puntero a CRYPT_DATA_BLOB para recibir la firma de marca de hora con codificación base64. Es responsabilidad del autor de la llamada liberar `pTimestampSignatureBlob` -> `pbData` después del `HepFree()` uso. Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

## <a name="remarks"></a>Observaciones

 La firma de marca de hora es en realidad un mensaje PKCS #7 SignedData cuyo contenido es el formato binario del SignatureValue de la firma de la licencia. Básicamente, actúa como contrafirma de la licencia.

## <a name="return-value"></a>Valor devuelto

 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.

## <a name="requirements"></a>Requisitos

**Ensamblado**: clr.dll

## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
