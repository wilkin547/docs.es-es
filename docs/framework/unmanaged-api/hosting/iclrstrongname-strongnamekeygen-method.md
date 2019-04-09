---
title: ICLRStrongName::StrongNameKeyGen (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abeb731ecd66e4412f904b085abcfc7b5b3a3c4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169785"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="cc004-102">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="cc004-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="cc004-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="cc004-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc004-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc004-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc004-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc004-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="cc004-106">[in] El nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="cc004-106">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="cc004-107">debe ser una cadena vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="cc004-107">must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cc004-108">[in] Un valor que especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="cc004-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="cc004-109">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="cc004-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="cc004-110">0 x 00000000: se usa cuando `wszKeyContainer` es nulo para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="cc004-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="cc004-111">0 x 00000001 (`SN_LEAVE_KEY`): Especifica que se debe registrar la clave izquierda.</span><span class="sxs-lookup"><span data-stu-id="cc004-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="cc004-112">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="cc004-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="cc004-113">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="cc004-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc004-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cc004-114">Return Value</span></span>  
 `S_OK` <span data-ttu-id="cc004-115">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="cc004-115">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc004-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc004-116">Remarks</span></span>  
 <span data-ttu-id="cc004-117">El [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) método crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="cc004-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="cc004-118">Después de recupera la clave, debe llamar a la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="cc004-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc004-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc004-119">Requirements</span></span>  
 <span data-ttu-id="cc004-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc004-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc004-121">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cc004-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cc004-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc004-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cc004-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cc004-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc004-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc004-124">See also</span></span>

- [<span data-ttu-id="cc004-125">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="cc004-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="cc004-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc004-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
