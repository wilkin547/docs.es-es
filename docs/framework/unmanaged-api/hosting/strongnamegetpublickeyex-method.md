---
title: StrongNameGetPublicKeyEx (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176232"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="df0d6-102">StrongNameGetPublicKeyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="df0d6-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="df0d6-103">Obtiene la clave pública de un par de claves pública y privada y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="df0d6-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df0d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df0d6-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="df0d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df0d6-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="df0d6-106">[en] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="df0d6-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="df0d6-107">Si `pbKeyBlob` es `szKeyContainer` null, debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="df0d6-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="df0d6-108">En este caso, el `StrongNameGetPublicKeyEx` método extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="df0d6-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="df0d6-109">Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.</span><span class="sxs-lookup"><span data-stu-id="df0d6-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="df0d6-110">Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="df0d6-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="df0d6-111">No se admiten otros tipos de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="df0d6-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="df0d6-112">[en] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="df0d6-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="df0d6-113">Este par tiene el formato creado `CryptExportKey` por la función Win32.</span><span class="sxs-lookup"><span data-stu-id="df0d6-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="df0d6-114">Si `pbKeyBlob` es null, se supone `szKeyContainer` que el contenedor de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="df0d6-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="df0d6-115">[en] El tamaño, en `pbKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="df0d6-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="df0d6-116">[fuera] La clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="df0d6-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="df0d6-117">Common `ppbPublicKeyBlob` Language Runtime asigna el parámetro y lo devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="df0d6-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="df0d6-118">El llamador debe liberar la memoria mediante el método [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="df0d6-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="df0d6-119">[fuera] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="df0d6-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="df0d6-120">[en] El algoritmo hash de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="df0d6-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="df0d6-121">Consulte la sección Comentarios para obtener una lista de valores aceptados.</span><span class="sxs-lookup"><span data-stu-id="df0d6-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="df0d6-122">[en] Reservado para uso futuro; de forma predeterminada es null.</span><span class="sxs-lookup"><span data-stu-id="df0d6-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df0d6-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df0d6-123">Return Value</span></span>  
 <span data-ttu-id="df0d6-124">`S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="df0d6-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df0d6-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df0d6-125">Remarks</span></span>  
 <span data-ttu-id="df0d6-126">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="df0d6-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df0d6-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df0d6-127">Remarks</span></span>  
 <span data-ttu-id="df0d6-128">En la tabla siguiente se muestra `uHashAlgId` el conjunto de valores aceptados para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="df0d6-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="df0d6-129">Nombre</span><span class="sxs-lookup"><span data-stu-id="df0d6-129">Name</span></span>|<span data-ttu-id="df0d6-130">Value</span><span class="sxs-lookup"><span data-stu-id="df0d6-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="df0d6-131">None</span><span class="sxs-lookup"><span data-stu-id="df0d6-131">None</span></span>|<span data-ttu-id="df0d6-132">0</span><span class="sxs-lookup"><span data-stu-id="df0d6-132">0</span></span>|  
|<span data-ttu-id="df0d6-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="df0d6-133">SHA-1</span></span>|<span data-ttu-id="df0d6-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="df0d6-134">0x8004</span></span>|  
|<span data-ttu-id="df0d6-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="df0d6-135">SHA-256</span></span>|<span data-ttu-id="df0d6-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="df0d6-136">0x800c</span></span>|  
|<span data-ttu-id="df0d6-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="df0d6-137">SHA-384</span></span>|<span data-ttu-id="df0d6-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="df0d6-138">0x800d</span></span>|  
|<span data-ttu-id="df0d6-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="df0d6-139">SHA-512</span></span>|<span data-ttu-id="df0d6-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="df0d6-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df0d6-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df0d6-141">Requirements</span></span>  
 <span data-ttu-id="df0d6-142">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df0d6-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df0d6-143">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="df0d6-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="df0d6-144">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df0d6-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df0d6-145">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df0d6-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0d6-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df0d6-146">See also</span></span>

- [<span data-ttu-id="df0d6-147">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="df0d6-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="df0d6-148">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="df0d6-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="df0d6-149">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df0d6-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="df0d6-150">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="df0d6-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
