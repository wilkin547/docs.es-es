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
ms.openlocfilehash: c8d97653a195ec0fc287455079f37b311c3d42e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508789"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="30d45-102">ICLRStrongName::StrongNameGetPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="30d45-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="30d45-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="30d45-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="30d45-104">El par de claves puede proporcionarse como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="30d45-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d45-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30d45-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30d45-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30d45-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="30d45-107">[in] Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="30d45-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="30d45-108">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del CSP.</span><span class="sxs-lookup"><span data-stu-id="30d45-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="30d45-109">En este caso, el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) método extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="30d45-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="30d45-110">Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="30d45-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="30d45-111">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) las claves de firma.</span><span class="sxs-lookup"><span data-stu-id="30d45-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="30d45-112">Se admite ningún otro tipo de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="30d45-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="30d45-113">[in] Un puntero a la par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="30d45-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="30d45-114">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="30d45-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="30d45-115">Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="30d45-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="30d45-116">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="30d45-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="30d45-117">[out] La clave pública BLOB devuelta.</span><span class="sxs-lookup"><span data-stu-id="30d45-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="30d45-118">El `ppbPublicKeyBlob` parámetro asignado por common language runtime y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="30d45-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="30d45-119">El llamador debe liberar la memoria utilizando la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="30d45-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="30d45-120">[out] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="30d45-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30d45-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30d45-121">Return Value</span></span>  
 <span data-ttu-id="30d45-122">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="30d45-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30d45-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30d45-123">Remarks</span></span>  
 <span data-ttu-id="30d45-124">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="30d45-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30d45-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30d45-125">Requirements</span></span>  
 <span data-ttu-id="30d45-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30d45-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d45-127">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="30d45-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="30d45-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30d45-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30d45-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30d45-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d45-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="30d45-130">See Also</span></span>  
 [<span data-ttu-id="30d45-131">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="30d45-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="30d45-132">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="30d45-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="30d45-133">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30d45-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
