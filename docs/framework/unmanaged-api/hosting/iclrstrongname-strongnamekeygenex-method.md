---
title: ICLRStrongName::StrongNameKeyGenEx (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93377f82992b8d7d55b21b53abfd7d7c2e9e620b
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075314"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="7cae7-102">ICLRStrongName::StrongNameKeyGenEx (Método)</span><span class="sxs-lookup"><span data-stu-id="7cae7-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="7cae7-103">Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para su uso de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="7cae7-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cae7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cae7-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cae7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7cae7-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="7cae7-106">[in] El nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="7cae7-106">[in] The requested key container name.</span></span> <span data-ttu-id="7cae7-107">`wszKeyContainer` debe ser una cadena vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="7cae7-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7cae7-108">[in] Un valor que especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="7cae7-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="7cae7-109">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7cae7-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="7cae7-110">0 x 00000000: se usa cuando `wszKeyContainer` es nulo para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="7cae7-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="7cae7-111">0 x 00000001 (`SN_LEAVE_KEY`): Especifica que se debe registrar la clave izquierda.</span><span class="sxs-lookup"><span data-stu-id="7cae7-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="7cae7-112">[in] El tamaño solicitado de la clave en bits.</span><span class="sxs-lookup"><span data-stu-id="7cae7-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="7cae7-113">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="7cae7-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="7cae7-114">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="7cae7-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cae7-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7cae7-115">Return Value</span></span>  
 <span data-ttu-id="7cae7-116">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="7cae7-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cae7-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7cae7-117">Remarks</span></span>  
 <span data-ttu-id="7cae7-118">Las versiones 1.0 y 1.1 de .NET Framework requieren una `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; versión 2.0 agrega compatibilidad para las claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="7cae7-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="7cae7-119">Después de recupera la clave, debe llamar a la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="7cae7-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cae7-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cae7-120">Requirements</span></span>  
 <span data-ttu-id="7cae7-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cae7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cae7-122">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7cae7-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7cae7-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cae7-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cae7-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cae7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cae7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cae7-125">See Also</span></span>  
 [<span data-ttu-id="7cae7-126">StrongNameKeyGen (método)</span><span class="sxs-lookup"><span data-stu-id="7cae7-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="7cae7-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cae7-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
