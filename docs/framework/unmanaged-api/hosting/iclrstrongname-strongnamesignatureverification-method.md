---
title: ICLRStrongName::StrongNameSignatureVerification (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
ms.openlocfilehash: 6375fd8e4a314403267a4cdf2e8356677e9e7a06
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899483"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="a7bb6-102">ICLRStrongName::StrongNameSignatureVerification (Método)</span><span class="sxs-lookup"><span data-stu-id="a7bb6-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="a7bb6-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba en función de las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7bb6-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7bb6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a7bb6-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a7bb6-106">de Ruta de acceso al archivo portable ejecutable (. dll o. exe) para que lo compruebe el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="a7bb6-107">de Marcas para modificar el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="a7bb6-108">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7bb6-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="a7bb6-109">`SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-109">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="a7bb6-110">`SN_INFLAG_INSTALL` (0x00000002): especifica que es la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-110">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="a7bb6-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-111">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="a7bb6-112">`SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado solo será accesible para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-112">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="a7bb6-113">`SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-113">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="a7bb6-114">`SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-114">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="a7bb6-115">enuncia Marcas que indican si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="a7bb6-116">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="a7bb6-116">The following value is supported:</span></span>  
  
- <span data-ttu-id="a7bb6-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a7bb6-117">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7bb6-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7bb6-118">Return Value</span></span>  
 <span data-ttu-id="a7bb6-119">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="a7bb6-119">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7bb6-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a7bb6-120">Requirements</span></span>  
 <span data-ttu-id="a7bb6-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7bb6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7bb6-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a7bb6-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a7bb6-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a7bb6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7bb6-124">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7bb6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bb6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7bb6-125">See also</span></span>

- [<span data-ttu-id="a7bb6-126">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="a7bb6-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="a7bb6-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7bb6-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
