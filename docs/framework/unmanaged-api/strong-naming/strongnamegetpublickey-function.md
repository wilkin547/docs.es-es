---
title: StrongNameGetPublicKey (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e38a85b688d66e9f44bd8026bb4c9e141a6eb7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229295"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="4a109-102">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="4a109-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="4a109-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="4a109-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="4a109-104">El par de claves puede proporcionarse como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="4a109-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="4a109-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="4a109-105">This function has been deprecated.</span></span> <span data-ttu-id="4a109-106">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4a109-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a109-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a109-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a109-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a109-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="4a109-109">[in] Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="4a109-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="4a109-110">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del CSP.</span><span class="sxs-lookup"><span data-stu-id="4a109-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="4a109-111">En este caso, `StrongNameGetPublicKey` extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="4a109-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="4a109-112">Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="4a109-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="4a109-113">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) las claves de firma.</span><span class="sxs-lookup"><span data-stu-id="4a109-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="4a109-114">Se admite ningún otro tipo de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="4a109-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="4a109-115">[in] Un puntero a la par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="4a109-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="4a109-116">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="4a109-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="4a109-117">Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="4a109-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="4a109-118">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="4a109-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="4a109-119">[out] La clave pública BLOB devuelta.</span><span class="sxs-lookup"><span data-stu-id="4a109-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="4a109-120">El `ppbPublicKeyBlob` parámetro asignado por common language runtime y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="4a109-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="4a109-121">El llamador debe liberar la memoria utilizando la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="4a109-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="4a109-122">[out] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="4a109-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a109-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4a109-123">Return Value</span></span>  
 `true` <span data-ttu-id="4a109-124">Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4a109-124">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a109-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a109-125">Remarks</span></span>  
 <span data-ttu-id="4a109-126">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="4a109-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="4a109-127">Si el `StrongNameGetPublicKey` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="4a109-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a109-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a109-128">Requirements</span></span>  
 <span data-ttu-id="4a109-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a109-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a109-130">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4a109-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4a109-131">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a109-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="4a109-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4a109-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a109-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a109-133">See also</span></span>

- [<span data-ttu-id="4a109-134">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="4a109-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="4a109-135">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="4a109-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="4a109-136">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a109-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="4a109-137">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4a109-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
