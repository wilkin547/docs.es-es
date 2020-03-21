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
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181936"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="1193c-102">ICLRStrongName::StrongNameGetPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="1193c-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="1193c-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="1193c-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="1193c-104">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección sin procesar de bytes.</span><span class="sxs-lookup"><span data-stu-id="1193c-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1193c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1193c-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1193c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1193c-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="1193c-107">[en] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="1193c-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="1193c-108">Si `pbKeyBlob` es `szKeyContainer` null, debe especificar un contenedor válido dentro del CSP.</span><span class="sxs-lookup"><span data-stu-id="1193c-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="1193c-109">En este caso, el método [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="1193c-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="1193c-110">Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.</span><span class="sxs-lookup"><span data-stu-id="1193c-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="1193c-111">Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="1193c-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="1193c-112">No se admiten otros tipos de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="1193c-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="1193c-113">[en] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="1193c-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="1193c-114">Este par tiene el formato creado `CryptExportKey` por la función Win32.</span><span class="sxs-lookup"><span data-stu-id="1193c-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="1193c-115">Si `pbKeyBlob` es null, se supone `szKeyContainer` que el contenedor de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="1193c-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="1193c-116">[en] El tamaño, en `pbKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="1193c-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="1193c-117">[fuera] La clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="1193c-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="1193c-118">Common `ppbPublicKeyBlob` Language Runtime asigna el parámetro y lo devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1193c-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="1193c-119">El llamador debe liberar la memoria mediante el método [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1193c-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="1193c-120">[fuera] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="1193c-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1193c-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1193c-121">Return Value</span></span>  
 <span data-ttu-id="1193c-122">`S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="1193c-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1193c-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1193c-123">Remarks</span></span>  
 <span data-ttu-id="1193c-124">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="1193c-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1193c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1193c-125">Requirements</span></span>  
 <span data-ttu-id="1193c-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1193c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1193c-127">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1193c-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1193c-128">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1193c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1193c-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1193c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1193c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1193c-130">See also</span></span>

- [<span data-ttu-id="1193c-131">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="1193c-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="1193c-132">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="1193c-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="1193c-133">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1193c-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
