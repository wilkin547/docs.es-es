---
title: "ICLRStrongName::StrongNameKeyGenEx (Método)"
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
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 581f486a2def90f44c0fb3f1bcf9d3bbcc1fc317
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="a247b-102">ICLRStrongName::StrongNameKeyGenEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a247b-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="a247b-103">Genera un nuevo par de claves pública/privada con el tamaño de clave especificado, para su uso de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a247b-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a247b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a247b-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a247b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a247b-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="a247b-106">[in] El nombre de contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="a247b-106">[in] The requested key container name.</span></span> <span data-ttu-id="a247b-107">`wszKeyContainer`debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="a247b-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a247b-108">[in] Un valor que especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="a247b-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="a247b-109">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a247b-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="a247b-110">0 x 00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="a247b-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="a247b-111">0 x 00000001 (`SN_LEAVE_KEY`)-especifica que la clave debería quedar registrada.</span><span class="sxs-lookup"><span data-stu-id="a247b-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="a247b-112">[in] El tamaño solicitado de la clave en bits.</span><span class="sxs-lookup"><span data-stu-id="a247b-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="a247b-113">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="a247b-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="a247b-114">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a247b-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a247b-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a247b-115">Return Value</span></span>  
 <span data-ttu-id="a247b-116">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="a247b-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a247b-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a247b-117">Remarks</span></span>  
 <span data-ttu-id="a247b-118">Las versiones de .NET Framework 1.0 y 1.1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2.0 también admite claves de 2048 bits de.</span><span class="sxs-lookup"><span data-stu-id="a247b-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="a247b-119">Una vez recuperada la clave, debe llamar a la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="a247b-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a247b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a247b-120">Requirements</span></span>  
 <span data-ttu-id="a247b-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a247b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a247b-122">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a247b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a247b-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a247b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a247b-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a247b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a247b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a247b-125">See Also</span></span>  
 [<span data-ttu-id="a247b-126">StrongNameKeyGen (método)</span><span class="sxs-lookup"><span data-stu-id="a247b-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="a247b-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a247b-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
