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
ms.openlocfilehash: 700bcc5b818c452d3642d325fb6fe19cbb162474
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141452"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="c82b5-102">StrongNameGetPublicKeyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="c82b5-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="c82b5-103">Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="c82b5-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c82b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c82b5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c82b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c82b5-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="c82b5-106">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c82b5-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="c82b5-107">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="c82b5-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="c82b5-108">En este caso, el método `StrongNameGetPublicKeyEx` extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="c82b5-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="c82b5-109">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="c82b5-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="c82b5-110">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="c82b5-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="c82b5-111">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="c82b5-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c82b5-112">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c82b5-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c82b5-113">Este par está en el formato creado por la función `CryptExportKey` de Win32.</span><span class="sxs-lookup"><span data-stu-id="c82b5-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c82b5-114">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="c82b5-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c82b5-115">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="c82b5-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c82b5-116">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="c82b5-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="c82b5-117">El Common Language Runtime asigna el parámetro `ppbPublicKeyBlob` y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c82b5-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="c82b5-118">El llamador debe liberar memoria mediante el método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c82b5-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c82b5-119">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="c82b5-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="c82b5-120">de Algoritmo hash del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c82b5-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="c82b5-121">Vea la sección Comentarios para obtener una lista de valores aceptados.</span><span class="sxs-lookup"><span data-stu-id="c82b5-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="c82b5-122">de Reservado para uso futuro; su valor predeterminado es NULL.</span><span class="sxs-lookup"><span data-stu-id="c82b5-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c82b5-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c82b5-123">Return Value</span></span>  
 <span data-ttu-id="c82b5-124">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="c82b5-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c82b5-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c82b5-125">Remarks</span></span>  
 <span data-ttu-id="c82b5-126">La clave pública está contenida en una estructura [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c82b5-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c82b5-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c82b5-127">Remarks</span></span>  
 <span data-ttu-id="c82b5-128">En la tabla siguiente se muestra el conjunto de valores aceptados para el parámetro `uHashAlgId`.</span><span class="sxs-lookup"><span data-stu-id="c82b5-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="c82b5-129">Name</span><span class="sxs-lookup"><span data-stu-id="c82b5-129">Name</span></span>|<span data-ttu-id="c82b5-130">Valor</span><span class="sxs-lookup"><span data-stu-id="c82b5-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="c82b5-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c82b5-131">None</span></span>|<span data-ttu-id="c82b5-132">0</span><span class="sxs-lookup"><span data-stu-id="c82b5-132">0</span></span>|  
|<span data-ttu-id="c82b5-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="c82b5-133">SHA-1</span></span>|<span data-ttu-id="c82b5-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="c82b5-134">0x8004</span></span>|  
|<span data-ttu-id="c82b5-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="c82b5-135">SHA-256</span></span>|<span data-ttu-id="c82b5-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="c82b5-136">0x800c</span></span>|  
|<span data-ttu-id="c82b5-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="c82b5-137">SHA-384</span></span>|<span data-ttu-id="c82b5-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="c82b5-138">0x800d</span></span>|  
|<span data-ttu-id="c82b5-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="c82b5-139">SHA-512</span></span>|<span data-ttu-id="c82b5-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="c82b5-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c82b5-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c82b5-141">Requirements</span></span>  
 <span data-ttu-id="c82b5-142">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c82b5-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c82b5-143">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="c82b5-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c82b5-144">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c82b5-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c82b5-145">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c82b5-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c82b5-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c82b5-146">See also</span></span>

- [<span data-ttu-id="c82b5-147">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="c82b5-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="c82b5-148">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="c82b5-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="c82b5-149">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c82b5-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="c82b5-150">StrongNameGetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="c82b5-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
