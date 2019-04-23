---
title: Authenticode (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408219307015d5c39cb581b3884ed9810f4c0566
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216358"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="ff866-102">Authenticode (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="ff866-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="ff866-103">Admite el módulo de creación y verificación de licencias Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="ff866-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff866-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff866-104">In This Section</span></span>  
 [<span data-ttu-id="ff866-105">_AxlGetIssuerPublicKeyHash (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="ff866-106">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="ff866-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="ff866-107">_AxlPublicKeyBlobToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="ff866-108">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="ff866-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="ff866-109">_AxlRSAKeyValueToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="ff866-110">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ff866-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="ff866-111">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="ff866-112">Libera recursos asignados para la estructura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="ff866-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="ff866-113">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="ff866-114">Libera recursos asignados para la estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="ff866-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="ff866-115">CertTimestampAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="ff866-116">Aplica marcas de hora a una licencia Authenticode XrML creada por CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="ff866-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="ff866-117">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="ff866-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="ff866-118">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="ff866-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="ff866-119">AXL_AUTHENTICODE_SIGNER_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="ff866-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="ff866-120">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="ff866-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="ff866-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="ff866-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="ff866-122">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="ff866-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff866-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff866-123">See also</span></span>

- [<span data-ttu-id="ff866-124">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="ff866-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
