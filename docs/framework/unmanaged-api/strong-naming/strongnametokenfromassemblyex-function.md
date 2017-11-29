---
title: "StrongNameTokenFromAssemblyEx (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameTokenFromAssemblyEx
helpviewer_keywords: StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef530595d92995124c590e70ac5ffc32a228c67a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="02d42-102">StrongNameTokenFromAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="02d42-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="02d42-103">Crea un token de nombre seguro del archivo de ensamblado especificado y devuelve la clave pública que representa el token.</span><span class="sxs-lookup"><span data-stu-id="02d42-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="02d42-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="02d42-104">This function has been deprecated.</span></span> <span data-ttu-id="02d42-105">Use la [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="02d42-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d42-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02d42-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02d42-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02d42-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="02d42-108">[in] La ruta de acceso al archivo ejecutable portable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02d42-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="02d42-109">[out] El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="02d42-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="02d42-110">[out] El tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="02d42-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="02d42-111">[out] La clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="02d42-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="02d42-112">[out] El tamaño, en bytes, de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="02d42-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d42-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="02d42-113">Return Value</span></span>  
 <span data-ttu-id="02d42-114">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="02d42-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d42-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02d42-115">Remarks</span></span>  
 <span data-ttu-id="02d42-116">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="02d42-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="02d42-117">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02d42-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="02d42-118">El token forma parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02d42-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="02d42-119">Después de recuperar la clave y se crea el token, debe llamar a la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="02d42-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="02d42-120">Si el `StrongNameTokenFromAssemblyEx` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="02d42-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d42-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02d42-121">Requirements</span></span>  
 <span data-ttu-id="02d42-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d42-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d42-123">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="02d42-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="02d42-124">**Biblioteca:** incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="02d42-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="02d42-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d42-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d42-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d42-126">See Also</span></span>  
 [<span data-ttu-id="02d42-127">StrongNameTokenFromAssemblyEx (método)</span><span class="sxs-lookup"><span data-stu-id="02d42-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="02d42-128">StrongNameTokenFromAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="02d42-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="02d42-129">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02d42-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
