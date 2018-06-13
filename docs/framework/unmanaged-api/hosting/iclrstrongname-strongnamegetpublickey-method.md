---
title: ICLRStrongName::StrongNameGetPublicKey (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b736e58a1a48a2bb4492b6b8ff58af1567babcf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434485"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="306b6-102">ICLRStrongName::StrongNameGetPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="306b6-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="306b6-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="306b6-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="306b6-104">El par de claves puede especificarse como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="306b6-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="306b6-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="306b6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="306b6-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="306b6-107">[in] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="306b6-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="306b6-108">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del CSP.</span><span class="sxs-lookup"><span data-stu-id="306b6-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="306b6-109">En este caso, el [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) método extrae la clave pública del par de claves que se almacenan en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="306b6-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="306b6-110">Si `pbKeyBlob` no es null, se supone que el par de claves para poder estar contenidos en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="306b6-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="306b6-111">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) claves de firma.</span><span class="sxs-lookup"><span data-stu-id="306b6-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="306b6-112">Ningún otro tipo de claves se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="306b6-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="306b6-113">[in] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="306b6-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="306b6-114">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="306b6-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="306b6-115">Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="306b6-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="306b6-116">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="306b6-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="306b6-117">[out] La clave pública BLOB devuelta.</span><span class="sxs-lookup"><span data-stu-id="306b6-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="306b6-118">El `ppbPublicKeyBlob` parámetro es asignado por common language runtime y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="306b6-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="306b6-119">El llamador debe liberar la memoria mediante el uso de la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="306b6-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="306b6-120">[out] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="306b6-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="306b6-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="306b6-121">Return Value</span></span>  
 <span data-ttu-id="306b6-122">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="306b6-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="306b6-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="306b6-123">Remarks</span></span>  
 <span data-ttu-id="306b6-124">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="306b6-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306b6-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="306b6-125">Requirements</span></span>  
 <span data-ttu-id="306b6-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306b6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306b6-127">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="306b6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="306b6-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="306b6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="306b6-129">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306b6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306b6-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="306b6-130">See Also</span></span>  
 [<span data-ttu-id="306b6-131">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="306b6-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="306b6-132">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="306b6-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="306b6-133">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="306b6-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
