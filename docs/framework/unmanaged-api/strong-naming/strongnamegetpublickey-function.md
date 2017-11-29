---
title: "StrongNameGetPublicKey (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameGetPublicKey
helpviewer_keywords: StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 243b5f8d94805d8631c7c79f424d9e6434213bb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="e0a93-102">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="e0a93-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="e0a93-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="e0a93-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="e0a93-104">El par de claves puede especificarse como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="e0a93-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="e0a93-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="e0a93-105">This function has been deprecated.</span></span> <span data-ttu-id="e0a93-106">Use la [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e0a93-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0a93-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0a93-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0a93-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0a93-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="e0a93-109">[in] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="e0a93-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="e0a93-110">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del CSP.</span><span class="sxs-lookup"><span data-stu-id="e0a93-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="e0a93-111">En este caso, `StrongNameGetPublicKey` extrae la clave pública del par de claves que se almacenan en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0a93-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="e0a93-112">Si `pbKeyBlob` no es null, se supone que el par de claves para poder estar contenidos en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="e0a93-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="e0a93-113">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) claves de firma.</span><span class="sxs-lookup"><span data-stu-id="e0a93-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="e0a93-114">Ningún otro tipo de claves se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="e0a93-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e0a93-115">[in] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="e0a93-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e0a93-116">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="e0a93-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e0a93-117">Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="e0a93-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e0a93-118">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e0a93-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="e0a93-119">[out] La clave pública BLOB devuelta.</span><span class="sxs-lookup"><span data-stu-id="e0a93-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="e0a93-120">El `ppbPublicKeyBlob` parámetro es asignado por common language runtime y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="e0a93-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="e0a93-121">El llamador debe liberar la memoria mediante el uso de la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="e0a93-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="e0a93-122">[out] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="e0a93-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0a93-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0a93-123">Return Value</span></span>  
 <span data-ttu-id="e0a93-124">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e0a93-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0a93-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0a93-125">Remarks</span></span>  
 <span data-ttu-id="e0a93-126">La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="e0a93-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="e0a93-127">Si el `StrongNameGetPublicKey` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="e0a93-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a93-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0a93-128">Requirements</span></span>  
 <span data-ttu-id="e0a93-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0a93-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0a93-130">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e0a93-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e0a93-131">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0a93-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0a93-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0a93-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a93-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0a93-133">See Also</span></span>  
 [<span data-ttu-id="e0a93-134">StrongNameGetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="e0a93-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="e0a93-135">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="e0a93-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="e0a93-136">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0a93-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="e0a93-137">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="e0a93-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
