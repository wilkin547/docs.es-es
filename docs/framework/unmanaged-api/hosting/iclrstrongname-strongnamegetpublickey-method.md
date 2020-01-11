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
ms.openlocfilehash: fd7f95ea01de397509c2a7b5fc08c0ac401a8da9
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899605"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="cdfbf-102">ICLRStrongName::StrongNameGetPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="cdfbf-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="cdfbf-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="cdfbf-104">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin procesar.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdfbf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdfbf-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdfbf-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="cdfbf-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="cdfbf-107">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="cdfbf-108">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el CSP.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="cdfbf-109">En este caso, el método [ICLRStrongName:: StrongNameGetPublicKey (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="cdfbf-110">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="cdfbf-111">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="cdfbf-112">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="cdfbf-113">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="cdfbf-114">Este par está en el formato creado por la función `CryptExportKey` de Win32.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="cdfbf-115">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="cdfbf-116">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="cdfbf-117">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="cdfbf-118">El Common Language Runtime asigna el parámetro `ppbPublicKeyBlob` y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="cdfbf-119">El llamador debe liberar memoria mediante el método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cdfbf-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="cdfbf-120">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="cdfbf-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdfbf-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cdfbf-121">Return Value</span></span>  
 <span data-ttu-id="cdfbf-122">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="cdfbf-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdfbf-123">Notas</span><span class="sxs-lookup"><span data-stu-id="cdfbf-123">Remarks</span></span>  
 <span data-ttu-id="cdfbf-124">La clave pública está contenida en una estructura [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="cdfbf-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdfbf-125">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="cdfbf-125">Requirements</span></span>  
 <span data-ttu-id="cdfbf-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdfbf-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdfbf-127">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="cdfbf-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cdfbf-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cdfbf-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdfbf-129">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdfbf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfbf-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdfbf-130">See also</span></span>

- [<span data-ttu-id="cdfbf-131">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="cdfbf-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="cdfbf-132">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="cdfbf-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="cdfbf-133">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdfbf-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
