---
title: CertTimestampAuthenticodeLicense (Función)
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
ms.openlocfilehash: fc1a99572406a38aee8133d6435134b78a134175
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674104"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="f14d4-102">CertTimestampAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="f14d4-102">CertTimestampAuthenticodeLicense Function</span></span>

<span data-ttu-id="f14d4-103">Aplica marcas de hora a una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="f14d4-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f14d4-104">Syntax</span></span>  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f14d4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f14d4-105">Parameters</span></span>  

 `pSignedLicenseBlob`  
 <span data-ttu-id="f14d4-106">[in] Licencia Authenticode XrML firmada a la que se va a aplicar la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="f14d4-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="f14d4-107">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="f14d4-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="f14d4-108">[in] URI del servidor de marca de hora.</span><span class="sxs-lookup"><span data-stu-id="f14d4-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="f14d4-109">[out] Puntero a CRYPT_DATA_BLOB para recibir la firma de marca de hora con codificación base64.</span><span class="sxs-lookup"><span data-stu-id="f14d4-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="f14d4-110">Es responsabilidad del autor de la llamada liberar `pTimestampSignatureBlob` -> `pbData` después del `HepFree()` uso.</span><span class="sxs-lookup"><span data-stu-id="f14d4-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="f14d4-111">Vea la estructura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="f14d4-111">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f14d4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f14d4-112">Remarks</span></span>  

 <span data-ttu-id="f14d4-113">La firma de marca de hora es en realidad un mensaje PKCS #7 SignedData cuyo contenido es el formato binario del SignatureValue de la firma de la licencia.</span><span class="sxs-lookup"><span data-stu-id="f14d4-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="f14d4-114">Básicamente, actúa como contrafirma de la licencia.</span><span class="sxs-lookup"><span data-stu-id="f14d4-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f14d4-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f14d4-115">Return Value</span></span>  

 <span data-ttu-id="f14d4-116">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f14d4-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="f14d4-117">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="f14d4-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14d4-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f14d4-118">See also</span></span>

- [<span data-ttu-id="f14d4-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f14d4-119">Authenticode</span></span>](index.md)
