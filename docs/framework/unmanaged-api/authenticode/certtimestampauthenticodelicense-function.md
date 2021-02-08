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
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="25671-103">CertTimestampAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="25671-103">CertTimestampAuthenticodeLicense Function</span></span>

<span data-ttu-id="25671-104">Aplica marcas de hora a una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="25671-104">Time-stamps an Authenticode XrML license.</span></span>

## <a name="syntax"></a><span data-ttu-id="25671-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25671-105">Syntax</span></span>

```cpp
HRESULT CertTimestampAuthenticodeLicense (
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,
    [in]  LPCWSTR            pwszTimestampURI,
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob
);
```

## <a name="parameters"></a><span data-ttu-id="25671-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25671-106">Parameters</span></span>

 `pSignedLicenseBlob`\
 <span data-ttu-id="25671-107">[in] Licencia Authenticode XrML firmada a la que se va a aplicar la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="25671-107">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="25671-108">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="25671-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `pwszTimestampURI`\
 <span data-ttu-id="25671-109">[in] URI del servidor de marca de hora.</span><span class="sxs-lookup"><span data-stu-id="25671-109">[in] The time-stamp server's URI.</span></span>

 `pTimestampSignatureBlob`\
 <span data-ttu-id="25671-110">[out] Puntero a CRYPT_DATA_BLOB para recibir la firma de marca de hora con codificación base64.</span><span class="sxs-lookup"><span data-stu-id="25671-110">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="25671-111">Es responsabilidad del autor de la llamada liberar `pTimestampSignatureBlob` -> `pbData` después del `HepFree()` uso.</span><span class="sxs-lookup"><span data-stu-id="25671-111">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="25671-112">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="25671-112">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

## <a name="remarks"></a><span data-ttu-id="25671-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="25671-113">Remarks</span></span>

 <span data-ttu-id="25671-114">La firma de marca de hora es en realidad un mensaje PKCS #7 SignedData cuyo contenido es el formato binario del SignatureValue de la firma de la licencia.</span><span class="sxs-lookup"><span data-stu-id="25671-114">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="25671-115">Básicamente, actúa como contrafirma de la licencia.</span><span class="sxs-lookup"><span data-stu-id="25671-115">Basically, this acts as a counter-signature of the license.</span></span>

## <a name="return-value"></a><span data-ttu-id="25671-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25671-116">Return Value</span></span>

 <span data-ttu-id="25671-117">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="25671-117">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="25671-118">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="25671-118">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="25671-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25671-119">Requirements</span></span>

<span data-ttu-id="25671-120">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="25671-120">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="25671-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="25671-121">See also</span></span>

- [<span data-ttu-id="25671-122">Authenticode</span><span class="sxs-lookup"><span data-stu-id="25671-122">Authenticode</span></span>](index.md)
