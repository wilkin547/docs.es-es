---
title: Authenticode (Referencia de la API no administrada)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e90a13ebf46f1891061c78435b7ba47d68de001d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="9d9e7-102">Authenticode (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="9d9e7-103">Admite el módulo de creación y verificación de licencias Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d9e7-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9d9e7-104">In This Section</span></span>  
 [<span data-ttu-id="9d9e7-105">_AxlGetIssuerPublicKeyHash (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="9d9e7-106">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="9d9e7-107">_AxlPublicKeyBlobToPublicKeyToken (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="9d9e7-108">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="9d9e7-109">_AxlRSAKeyValueToPublicKeyToken (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="9d9e7-110">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="9d9e7-111">CertFreeAuthenticodeSignerInfo (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="9d9e7-112">Libera recursos asignados para la estructura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="9d9e7-113">CertFreeAuthenticodeTimestamperInfo (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="9d9e7-114">Libera recursos asignados para la estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="9d9e7-115">CertTimestampAuthenticodeLicense (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="9d9e7-116">Aplica marcas de hora a una licencia Authenticode XrML creada por CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="9d9e7-117">CertVerifyAuthenticodeLicense (función)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="9d9e7-118">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="9d9e7-119">AXL_AUTHENTICODE_SIGNER_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="9d9e7-120">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="9d9e7-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="9d9e7-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="9d9e7-122">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="9d9e7-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9e7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d9e7-123">See Also</span></span>  
 [<span data-ttu-id="9d9e7-124">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="9d9e7-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
