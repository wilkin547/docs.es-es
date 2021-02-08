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
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="b811e-103">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="b811e-103">CertVerifyAuthenticodeLicense Function</span></span>

<span data-ttu-id="b811e-104">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="b811e-104">Verifies the validity of an Authenticode XrML license.</span></span>

## <a name="syntax"></a><span data-ttu-id="b811e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b811e-105">Syntax</span></span>

```cpp
HRESULT CertVerifyAuthenticodeLicense (
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,
    [in]   OPTIONAL DWORD                     dwFlags,
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo
);
```

## <a name="parameters"></a><span data-ttu-id="b811e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b811e-106">Parameters</span></span>

 `pLicenseBlob`\
 <span data-ttu-id="b811e-107">[in] Licencia Authenticode XrML que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="b811e-107">[in] The Authenticode XrML license to be verified.</span></span>

 <span data-ttu-id="b811e-108">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="b811e-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `dwFlags`\
 <span data-ttu-id="b811e-109">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="b811e-109">[in] Optional.</span></span> <span data-ttu-id="b811e-110">Una combinación de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b811e-110">A combination of following values:</span></span>

- <span data-ttu-id="b811e-111">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="b811e-111">AXL_REVOCATION_NO_CHECK</span></span>

- <span data-ttu-id="b811e-112">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="b811e-112">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>

- <span data-ttu-id="b811e-113">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="b811e-113">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>

- <span data-ttu-id="b811e-114">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="b811e-114">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>

- <span data-ttu-id="b811e-115">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="b811e-115">AXL_LIFETIME_SIGNING</span></span>

- <span data-ttu-id="b811e-116">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="b811e-116">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>

 `pSignerInfo`\
 <span data-ttu-id="b811e-117">[out] Para recibir la información del firmante.</span><span class="sxs-lookup"><span data-stu-id="b811e-117">[out] To receive the signer's information.</span></span> <span data-ttu-id="b811e-118">Si la licencia no estaba firmada, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="b811e-118">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="b811e-119">Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodesignerinfo (](certfreeauthenticodesignerinfo-function.md) después del uso.</span><span class="sxs-lookup"><span data-stu-id="b811e-119">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>

 <span data-ttu-id="b811e-120">Vea [estructura de AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b811e-120">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>

 `pTimestamperInfo`\
 <span data-ttu-id="b811e-121">[out] Para recibir la información del autor de la marca de hora, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="b811e-121">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="b811e-122">Si la licencia no tenía marca de hora, `dwError` se establece en TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="b811e-122">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="b811e-123">Es responsabilidad del autor de la llamada liberar recursos mediante la función [certfreeauthenticodetimestamperinfo (](certfreeauthenticodetimestamperinfo-function.md) después del uso.</span><span class="sxs-lookup"><span data-stu-id="b811e-123">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>

 <span data-ttu-id="b811e-124">Vea [estructura de AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b811e-124">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>

## <a name="return-value"></a><span data-ttu-id="b811e-125">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b811e-125">Return Value</span></span>

 <span data-ttu-id="b811e-126">Si la operación se realiza correctamente, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="b811e-126">Returns `S_OK` if successful.</span></span> <span data-ttu-id="b811e-127">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="b811e-127">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="b811e-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b811e-128">Requirements</span></span>

<span data-ttu-id="b811e-129">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="b811e-129">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="b811e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b811e-130">See also</span></span>

- [<span data-ttu-id="b811e-131">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b811e-131">Authenticode</span></span>](index.md)
- [<span data-ttu-id="b811e-132">Método GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="b811e-132">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="b811e-133">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b811e-133">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
