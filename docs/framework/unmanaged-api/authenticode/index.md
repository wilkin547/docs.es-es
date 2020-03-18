---
title: Authenticode (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 1b8b2222950c75f7f9d2ec2704f722087645cd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132464"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="01e62-102">Authenticode (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="01e62-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="01e62-103">Admite el módulo de creación y verificación de licencias Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="01e62-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01e62-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="01e62-104">In This Section</span></span>  
 [<span data-ttu-id="01e62-105">_AxlGetIssuerPublicKeyHash (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="01e62-106">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="01e62-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="01e62-107">_AxlPublicKeyBlobToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="01e62-108">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="01e62-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="01e62-109">_AxlRSAKeyValueToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="01e62-110">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="01e62-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="01e62-111">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="01e62-112">Libera recursos asignados para la estructura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="01e62-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="01e62-113">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="01e62-114">Libera recursos asignados para la estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="01e62-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="01e62-115">CertTimestampAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="01e62-116">Aplica marcas de hora a una licencia Authenticode XrML creada por CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="01e62-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="01e62-117">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="01e62-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="01e62-118">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="01e62-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="01e62-119">AXL_AUTHENTICODE_SIGNER_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="01e62-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="01e62-120">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="01e62-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="01e62-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="01e62-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="01e62-122">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="01e62-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e62-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="01e62-123">See also</span></span>

- [<span data-ttu-id="01e62-124">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="01e62-124">Unmanaged API Reference</span></span>](../index.md)
