---
title: "StrongNameGetPublicKeyEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e94498cc8841a95e1918d3f26bd19256793564ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="f9115-102">StrongNameGetPublicKeyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="f9115-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="f9115-103">Obtiene la clave pública de un par de claves pública y privada y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="f9115-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9115-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9115-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9115-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9115-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="f9115-106">[in] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="f9115-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="f9115-107">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="f9115-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="f9115-108">En este caso, el `StrongNameGetPublicKeyEx` método extrae la clave pública del par de claves que se almacenan en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f9115-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="f9115-109">Si `pbKeyBlob` no es null, se supone que el par de claves para poder estar contenidos en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="f9115-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f9115-110">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) claves de firma.</span><span class="sxs-lookup"><span data-stu-id="f9115-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f9115-111">Ningún otro tipo de claves se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="f9115-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f9115-112">[in] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="f9115-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f9115-113">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="f9115-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f9115-114">Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="f9115-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f9115-115">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f9115-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f9115-116">[out] La clave pública BLOB devuelta.</span><span class="sxs-lookup"><span data-stu-id="f9115-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="f9115-117">El `ppbPublicKeyBlob` parámetro es asignado por common language runtime y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="f9115-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="f9115-118">El llamador debe liberar la memoria mediante el uso de la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f9115-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f9115-119">[out] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="f9115-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="f9115-120">[in] El algoritmo de hash de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f9115-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="f9115-121">Vea la sección Comentarios para obtener una lista de valores que se aceptan.</span><span class="sxs-lookup"><span data-stu-id="f9115-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="f9115-122">[in] Reservado para uso futuro; el valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="f9115-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9115-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f9115-123">Return Value</span></span>  
 <span data-ttu-id="f9115-124">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="f9115-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9115-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9115-125">Remarks</span></span>  
 <span data-ttu-id="f9115-126">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="f9115-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9115-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9115-127">Remarks</span></span>  
 <span data-ttu-id="f9115-128">En la tabla siguiente muestra el conjunto de valores aceptados para el `uHashAlgId` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f9115-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="f9115-129">nombre</span><span class="sxs-lookup"><span data-stu-id="f9115-129">Name</span></span>|<span data-ttu-id="f9115-130">Valor</span><span class="sxs-lookup"><span data-stu-id="f9115-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="f9115-131">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f9115-131">None</span></span>|<span data-ttu-id="f9115-132">0</span><span class="sxs-lookup"><span data-stu-id="f9115-132">0</span></span>|  
|<span data-ttu-id="f9115-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="f9115-133">SHA-1</span></span>|<span data-ttu-id="f9115-134">0 x 8004</span><span class="sxs-lookup"><span data-stu-id="f9115-134">0x8004</span></span>|  
|<span data-ttu-id="f9115-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="f9115-135">SHA-256</span></span>|<span data-ttu-id="f9115-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="f9115-136">0x800c</span></span>|  
|<span data-ttu-id="f9115-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="f9115-137">SHA-384</span></span>|<span data-ttu-id="f9115-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="f9115-138">0x800d</span></span>|  
|<span data-ttu-id="f9115-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="f9115-139">SHA-512</span></span>|<span data-ttu-id="f9115-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="f9115-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9115-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9115-141">Requirements</span></span>  
 <span data-ttu-id="f9115-142">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9115-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9115-143">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f9115-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f9115-144">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9115-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9115-145">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9115-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9115-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9115-146">See Also</span></span>  
 [<span data-ttu-id="f9115-147">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="f9115-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="f9115-148">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="f9115-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="f9115-149">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9115-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="f9115-150">StrongNameGetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="f9115-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
