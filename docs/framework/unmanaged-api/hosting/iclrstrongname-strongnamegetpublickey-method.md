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
ms.openlocfilehash: 5bd314b2b63474d2a1d159f74564e2d4ca13aef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725552"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="977c6-102">ICLRStrongName::StrongNameGetPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="977c6-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>

<span data-ttu-id="977c6-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="977c6-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="977c6-104">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin procesar.</span><span class="sxs-lookup"><span data-stu-id="977c6-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="977c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="977c6-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="977c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="977c6-106">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="977c6-107">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="977c6-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="977c6-108">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el CSP.</span><span class="sxs-lookup"><span data-stu-id="977c6-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="977c6-109">En este caso, el método [ICLRStrongName:: StrongNameGetPublicKey (](iclrstrongname-strongnamegetpublickey-method.md) extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="977c6-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="977c6-110">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="977c6-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="977c6-111">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="977c6-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="977c6-112">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="977c6-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="977c6-113">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="977c6-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="977c6-114">Este par está en el formato creado por la función de Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="977c6-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="977c6-115">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="977c6-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="977c6-116">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="977c6-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="977c6-117">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="977c6-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="977c6-118">El `ppbPublicKeyBlob` Common Language Runtime asigna el parámetro y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="977c6-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="977c6-119">El llamador debe liberar memoria mediante el método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="977c6-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="977c6-120">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="977c6-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="977c6-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="977c6-121">Return Value</span></span>  

 <span data-ttu-id="977c6-122">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="977c6-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="977c6-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="977c6-123">Remarks</span></span>  

 <span data-ttu-id="977c6-124">La clave pública está contenida en una estructura [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="977c6-124">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="977c6-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="977c6-125">Requirements</span></span>  

 <span data-ttu-id="977c6-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="977c6-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="977c6-127">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="977c6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="977c6-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="977c6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="977c6-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="977c6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="977c6-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="977c6-130">See also</span></span>

- [<span data-ttu-id="977c6-131">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="977c6-131">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="977c6-132">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="977c6-132">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="977c6-133">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="977c6-133">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
