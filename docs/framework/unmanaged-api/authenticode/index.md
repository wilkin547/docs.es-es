---
description: 'Más información acerca de: Authenticode (Referencia de la API no administrada)'
title: Authenticode (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 0a4a9b4ba3cc9a5818896508c80bc31073f514e7
ms.sourcegitcommit: 26721a2260deabb3318cc98af8619306711153cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "105027849"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="fdc4d-103">Authenticode (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-103">Authenticode (Unmanaged API Reference)</span></span>

<span data-ttu-id="fdc4d-104">Admite el módulo de creación y verificación de licencias Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-104">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdc4d-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fdc4d-105">In This Section</span></span>  

 [<span data-ttu-id="fdc4d-106">_AxlGetIssuerPublicKeyHash (Función)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-106">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="fdc4d-107">Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-107">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="fdc4d-108">_AxlPublicKeyBlobToPublicKeyToken (Función)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-108">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="fdc4d-109">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-109">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="fdc4d-110">Función _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="fdc4d-110">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="fdc4d-111">Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-111">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="fdc4d-112">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-112">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="fdc4d-113">Libera recursos asignados para la estructura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-113">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="fdc4d-114">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-114">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="fdc4d-115">Libera recursos asignados para la estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-115">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="fdc4d-116">CertTimestampAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-116">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="fdc4d-117">Aplica marcas de hora a una licencia Authenticode XrML creada por CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-117">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="fdc4d-118">CertVerifyAuthenticodeLicense (Función)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-118">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="fdc4d-119">Comprueba la validez de una licencia Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-119">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="fdc4d-120">AXL_AUTHENTICODE_SIGNER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-120">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="fdc4d-121">Define la información del firmante de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-121">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="fdc4d-122">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fdc4d-122">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="fdc4d-123">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fdc4d-123">Defines the Authenticode time stamper information.</span></span>  

## <a name="requirements"></a><span data-ttu-id="fdc4d-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdc4d-124">Requirements</span></span>

<span data-ttu-id="fdc4d-125">**Biblioteca**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="fdc4d-125">**Library**: clr.dll</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdc4d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdc4d-126">See also</span></span>

- [<span data-ttu-id="fdc4d-127">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="fdc4d-127">Unmanaged API Reference</span></span>](../index.md)
