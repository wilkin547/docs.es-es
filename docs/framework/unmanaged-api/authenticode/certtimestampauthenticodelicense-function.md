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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b110adac8c1ae68a3918a9e0fdf3f3eb4d017f0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406213"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="3f49c-102">CertTimestampAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="3f49c-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="3f49c-103">Aplica marcas de hora a una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="3f49c-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f49c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f49c-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f49c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f49c-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="3f49c-106">[in] Licencia Authenticode XrML firmada a la que se va a aplicar la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="3f49c-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="3f49c-107">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="3f49c-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="3f49c-108">[in] URI del servidor de marca de hora.</span><span class="sxs-lookup"><span data-stu-id="3f49c-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="3f49c-109">[out] Puntero a CRYPT_DATA_BLOB para recibir la firma de marca de hora con codificación base64.</span><span class="sxs-lookup"><span data-stu-id="3f49c-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="3f49c-110">Es responsabilidad del llamante liberar `pTimestampSignatureBlob` -> `pbData` con `HepFree()` tras su uso.</span><span class="sxs-lookup"><span data-stu-id="3f49c-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="3f49c-111">Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="3f49c-111">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f49c-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f49c-112">Remarks</span></span>  
 <span data-ttu-id="3f49c-113">La firma de marca de hora es en realidad un mensaje PKCS #7 SignedData cuyo contenido es el formato binario del SignatureValue de la firma de la licencia.</span><span class="sxs-lookup"><span data-stu-id="3f49c-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="3f49c-114">Básicamente, actúa como contrafirma de la licencia.</span><span class="sxs-lookup"><span data-stu-id="3f49c-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f49c-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f49c-115">Return Value</span></span>  
 <span data-ttu-id="3f49c-116">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f49c-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="3f49c-117">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="3f49c-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f49c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f49c-118">See Also</span></span>  
 [<span data-ttu-id="3f49c-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3f49c-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
