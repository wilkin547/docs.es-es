---
description: 'Más información sobre: ICLRStrongName:: Strongnamesignatureverification ((método)'
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
ms.openlocfilehash: 985a00ffe464f2dd6a92c299dae14206fd37a898
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781849"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="1516f-103">ICLRStrongName::StrongNameSignatureVerification (Método)</span><span class="sxs-lookup"><span data-stu-id="1516f-103">ICLRStrongName::StrongNameSignatureVerification Method</span></span>

<span data-ttu-id="1516f-104">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba en función de las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="1516f-104">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1516f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1516f-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1516f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1516f-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="1516f-107">de Ruta de acceso al archivo portable ejecutable (. dll o. exe) para que lo compruebe el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1516f-107">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="1516f-108">de Marcas para modificar el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="1516f-108">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="1516f-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="1516f-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="1516f-110">`SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="1516f-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="1516f-111">`SN_INFLAG_INSTALL` (0x00000002): especifica que esta es la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="1516f-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="1516f-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="1516f-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="1516f-113">`SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado será accesible únicamente para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="1516f-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="1516f-114">`SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="1516f-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="1516f-115">`SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="1516f-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="1516f-116">enuncia Marcas que indican si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="1516f-116">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="1516f-117">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="1516f-117">The following value is supported:</span></span>  
  
- <span data-ttu-id="1516f-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="1516f-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1516f-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1516f-119">Return Value</span></span>  

 <span data-ttu-id="1516f-120">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="1516f-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1516f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1516f-121">Requirements</span></span>  

 <span data-ttu-id="1516f-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1516f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1516f-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="1516f-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1516f-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1516f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1516f-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1516f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1516f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1516f-126">See also</span></span>

- [<span data-ttu-id="1516f-127">Método StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="1516f-127">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="1516f-128">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1516f-128">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
