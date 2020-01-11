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
ms.openlocfilehash: e437ee2ab04d3b1126ec2911553e87586e74e54e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899614"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="d47ac-102">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="d47ac-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="d47ac-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="d47ac-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d47ac-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d47ac-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d47ac-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="d47ac-106">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="d47ac-106">[in] The requested key container name.</span></span> <span data-ttu-id="d47ac-107">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="d47ac-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d47ac-108">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="d47ac-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="d47ac-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d47ac-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="d47ac-110">0x00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="d47ac-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="d47ac-111">0x00000001 (`SN_LEAVE_KEY`): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="d47ac-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="d47ac-112">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="d47ac-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="d47ac-113">enuncia Tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d47ac-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d47ac-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d47ac-114">Return Value</span></span>  
 <span data-ttu-id="d47ac-115">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="d47ac-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d47ac-116">Notas</span><span class="sxs-lookup"><span data-stu-id="d47ac-116">Remarks</span></span>  
 <span data-ttu-id="d47ac-117">El método [ICLRStrongName:: strongnamekeygen (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="d47ac-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="d47ac-118">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="d47ac-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47ac-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d47ac-119">Requirements</span></span>  
 <span data-ttu-id="d47ac-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d47ac-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47ac-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d47ac-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d47ac-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d47ac-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d47ac-123">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47ac-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47ac-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d47ac-124">See also</span></span>

- [<span data-ttu-id="d47ac-125">StrongNameKeyGenEx (método)</span><span class="sxs-lookup"><span data-stu-id="d47ac-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="d47ac-126">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d47ac-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
