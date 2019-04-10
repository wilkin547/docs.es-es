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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9fb7098c29768821cafad6662b646eb0e08a138
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212848"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="c51c5-102">ICLRStrongName::StrongNameSignatureVerification (Método)</span><span class="sxs-lookup"><span data-stu-id="c51c5-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="c51c5-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="c51c5-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c51c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c51c5-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c51c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c51c5-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c51c5-106">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado comprobar.</span><span class="sxs-lookup"><span data-stu-id="c51c5-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="c51c5-107">[in] Marcas para modificar el comportamiento de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c51c5-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="c51c5-108">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c51c5-108">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="c51c5-109">(0 x 00000001) - fuerza la comprobación incluso si es necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="c51c5-109">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="c51c5-110">(0 x 00000002): Especifica que se trata de la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="c51c5-110">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="c51c5-111">(0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="c51c5-111">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="c51c5-112">(0 x 00000008): Especifica que el ensamblado será accesible solo para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="c51c5-112">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="c51c5-113">(0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="c51c5-113">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="c51c5-114">(0 x 80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="c51c5-114">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="c51c5-115">[out] Marcas que indican si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c51c5-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="c51c5-116">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="c51c5-116">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="c51c5-117">(0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="c51c5-117">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c51c5-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c51c5-118">Return Value</span></span>  
 `S_OK` <span data-ttu-id="c51c5-119">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="c51c5-119">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c51c5-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c51c5-120">Requirements</span></span>  
 <span data-ttu-id="c51c5-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c51c5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c51c5-122">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c51c5-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c51c5-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c51c5-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c51c5-124">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c51c5-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c51c5-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c51c5-125">See also</span></span>

- [<span data-ttu-id="c51c5-126">Método StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="c51c5-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="c51c5-127">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c51c5-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
